## Deploy to Github Pages

Deploy requires [`cr`](https://github.com/helm/chart-releaser) tool

### Enable Github Pages (only first time)

Settings > Options > Github Pages > Source > Select your branch

### Package chart

```
helm package charts/<chart-to-package> --destination .deploy
```

### Upload New Release

```
cr upload --config config.yaml --token <github-deploy-token>
```

### Generate new index
```
cr index --config config.yaml
git add index.yaml
git commit -m "Update index.yaml"
git push
```
