# Certified Kubernetes Administrator (CKA) – Hands-on Portfolio

Dieses Repository dokumentiert meine praktische Vorbereitung auf die **Certified Kubernetes Administrator (CKA)** Zertifizierung auf Basis des KodeKloud-Kurses *"Certified Kubernetes Administrator (CKA) with Practice Tests"*.

Es enthält praxisnahe Kubernetes-Manifeste, Cluster-Konfigurationen und ausführliche Troubleshooting-Logbücher aus realen Lab-Szenarien.

## 🛠 Repository-Struktur & Themen

- **`01-architecture-design/`**: Cluster-Architektur, Control Plane Komponenten, Static Pods und etcd Backup/Restore.
- **`02-workloads-services/`**: Multi-Container Pods, Deployments, Services (ClusterIP, NodePort) und Ingress-Controller.
- **`03-storage/`**: Persistent Volumes (PV), Persistent Volume Claims (PVC) und dynamic Provisioning mit StorageClasses.
- **`04-troubleshooting/`**: Analyse und Behebung von Fehlern auf Application-, Control Plane- und Worker Node-Ebene.
- **`05-security/`**: Role-Based Access Control (RBAC), ServiceAccounts und SecurityContexts.

## 🔍 Fokus: Troubleshooting & Lab-Praxis

Ein zentraler Bestandteil meiner Vorbereitung war das gezielte Beheben von Cluster-Fehlern. Im Ordner `04-troubleshooting/` finden sich detaillierte Post-Mortem-Analysen zu Themen wie:
- `CrashLoopBackOff` & Pod-Diagnose via `kubectl logs` / `describe`
- CoreDNS-Ausfälle & Netzwerk-Debugging
- Node `NotReady`-Zustände (Kubelet / Container Runtime Fehler)

---
*Erstellt & gepflegt im Rahmen des KodeKloud CKA Intensive Trainings.*# CKA Lab & Kubernetes Showcase


