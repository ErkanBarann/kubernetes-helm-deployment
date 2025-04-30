## Helm Repository Ekleme ve Uygulama Kurulumu

### 1. Helm Repository Ekleme

```bash
helm repo add Helm-Application-Repo 'https://raw.githubusercontent.com/<github-user-name>/Helm-Application-Repo/main'
```

### 2. Todo Uygulamasını Kurma

```bash
helm install github-repo-release-todo Helm-Application-Repo/todochart
```

### 3. Guestbook Uygulamasını Kurma

```bash
helm install github-repo-release-guest Helm-Application-Repo/Guestbook