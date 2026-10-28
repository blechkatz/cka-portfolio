# Fall 01: Pod startet nicht (CrashLoopBackOff)

## Problem
Der Pod 'websever-pod' bleibt im Status 'CrashLoopBackOff' hängen und startet dauernd neu.

## Diagnose
Befehl ausgeführt: 'kubectl logs webserver-pod'
**Fehlermeldung:** 'Configuration error: missing port definition'

## Lösung
In der YAML-Datei fehlte die Port-Angabe. Nach dem hinzufügen von 'containerPort: 80' lief der Port stabil.

Befehl zum Anwenden: 'kubectl apply -f pod-config.yaml'
