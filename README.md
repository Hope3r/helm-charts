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
helm package charts/nginx -d .packages
helm repo index .packages --url https://hope3r.github.io/helm-charts/
Modifier les urls dans index.yaml (https://hope3r.github.io/helm-charts/nginx-0.1.8.tgz -> https://github.com/Hope3r/helm-charts/releases/download/nginx-0.1.8/nginx-0.1.8.tgz)
cr upload --config config.yaml --skip-existing
git commit .packages/index.yaml -m "release <package_version>"
git push
```