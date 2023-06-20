# helm-charts

This is a repository for serving different customised public helm charts from github. 

In order to see how we serve customised helm charts from github, you can follow the below link:
```
https://medium.com/@mattiaperi/create-a-public-helm-chart-repository-with-github-pages-49b180dbb417
```

### Creating new helm charts. 

In order to create a new customised helm chart, the following steps should be run:

1. Clone the repository to your local machine and go to the root of the repository.
2. Run the following command to create a new helm chart with `<HELM_CHART_NAME>` replaced with the name you chose for the chart.
```
helm create helm-chart-sources/<HELM_CHART_NAME>
```

After running the above command, a new directory named `<HELM_CHART_NAME` is created in the `helm-chart-sources` directory.

3. Go to the directory created in step 2 and change the templates as you want.
4. Run the following command to have the newly created chart packaged and the `tgz` file is created for it.
```
helm package helm-chart-sources/<HELM_CHART_NAME>
```
5. Run the below command to change the `index.yaml` file to have the changes related to the newly created chart.
```
helm repo index --url https://soroushkhosravi.github.io/helm-charts/ .
```

The link that comes after of the `--url` flag is the address of the page created for the repository by the `github`. 