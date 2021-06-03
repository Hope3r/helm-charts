# helm-charts

## Utilisation

Mettre ses charts dans un dossier ./charts

Créer un fichier de conf config.yaml sous la forme :
```yaml
owner: Hope3r
git-repo: helm-charts
charts-repo: helm-charts
package-path: .packages
token: <github_token>
index-path: ./index
```

```yaml
helm package charts/<app> -d .packages
cr upload --config config.yaml --skip-existing
helm repo index . --url https://hope3r.github.io/helm-charts/releases/download/<package_version> --merge index.yaml
git commit index.yaml -m "release <package_version>"
git push
```