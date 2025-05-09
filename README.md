# 📦 Helm Chart Repository for Guestbook & Todo Applications

This repository contains Helm charts for deploying two sample applications — **Guestbook** and **Todo App** — on a Kubernetes cluster. The charts are packaged, indexed, and published to simulate a functional Helm chart repository.

## 📚 Contents

- `Guestbook-0.1.0.tgz` – Helm package for the Guestbook app  
- `todochart-0.1.0.tgz` – Helm package for the Todo app (v1)  
- `todochart-0.2.0.tgz` – Updated chart version  
- `index.yaml` – Helm repository index file generated via `helm repo index`

## 🛠️ How the Helm Repository Was Created

1. **Chart creation** (for each app):

   ```bash
   helm create guestbook
   helm create todochart
   ```

2. **Update the chart templates and values.yaml** according to app configs.

3. **Package the charts**:

   ```bash
   helm package guestbook/
   helm package todochart/
   ```

   This generates `.tgz` files for each chart.

4. **Generate `index.yaml`** to create a Helm repository structure:

   ```bash
   helm repo index . --url https://raw.githubusercontent.com/<your-username>/<repo-name>/main/
   ```

5. **Push files to GitHub**:

   All `.tgz` packages and the `index.yaml` file were committed and pushed to GitHub — this forms a custom Helm repository that can be consumed by `helm repo add`.

## 🧰 Prerequisites

- A running **Kubernetes cluster**
- [Helm v3+](https://helm.sh/)
- Public access to the GitHub repository or GitHub Pages

## 🚀 Add Helm Repository

```bash
helm repo add helm-apps-repo 'https://raw.githubusercontent.com/<your-username>/<repo-name>/main/'
helm repo update
```

## 📦 Install Todo App

```bash
helm install todo-release helm-apps-repo/todochart
```

Install a specific version:

```bash
helm install todo-release helm-apps-repo/todochart --version 0.2.0
```

## 💬 Install Guestbook App

```bash
helm install guest-release helm-apps-repo/Guestbook
```

## 🔄 Upgrade or Uninstall

```bash
helm upgrade todo-release helm-apps-repo/todochart --version 0.2.0
helm uninstall todo-release
helm uninstall guest-release
```

## 📁 Directory Structure

```
├── Guestbook-0.1.0.tgz
├── todochart-0.1.0.tgz
├── todochart-0.2.0.tgz
├── index.yaml
└── README.md
```

## 📝 License

MIT © Erkan Baran
