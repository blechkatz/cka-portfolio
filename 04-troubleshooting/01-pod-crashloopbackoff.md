# Case Study 01: Behebung von CrashLoopBackOff (Falsches Container-Command)

Szenario aus KodeKloud Lab:  
Nach dem Deployment der Anwendung webapp-auth meldet Kubernetes den Status CrashLoopBackOff. Die Anwendung startet immer wieder neu und geht nicht in den Zustand Running.

## 1. Fehlerdiagnose (Troubleshooting Steps)

Zuerst prüfen wir den Status des Pods im Ziel-Namespace:

  kubectl get pods -n production

Ergebnis: webapp-auth-7d8b9c6-x8z2p   0/1   CrashLoopBackOff   4 (45s ago)

Um die genaue Ursache zu ermitteln, schauen wir in die Events und Logs des Containers:

  kubectl describe pod webapp-auth-7d8b9c6-x8z2p -n production
  kubectl logs webapp-auth-7d8b9c6-x8z2p -n production --previous

Analyse der Log-Ausgabe:
  Error: unknown command "start-server" for "python3"

## 2. Ursachenanalyse (Root Cause)

In der Pod-Spezifikation (spec.containers[].command) wurde der Befehl ["python3", "start-server"] angegeben. Das Skript heißt im Container jedoch server.py.

## 3. Lösung (Resolution)

Das Deployment direkt bearbeiten:

  kubectl edit deployment webapp-auth -n production

Den Befehl in der Spezifikation korrigieren:

  spec:
    containers:
    - name: webapp
      image: python:3.9-slim
      command: ["python3", "server.py"]

## 4. Verifizierung

Nach dem Speichern Rollout abwarten und Status erneut prüfen:

  kubectl get pods -n production -w

Ergebnis: webapp-auth-7d8b9c6-k2m9l   1/1   Running
