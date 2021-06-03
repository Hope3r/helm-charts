# helm-charts

## Utilisation

Mettre ses charts dans un dossier ./charts

```yaml
helm package charts/<app>
helm repo index --url https://hope3r.github.io/helm-charts/releases/download/<package_version> .
```