helm charts:

commands:
helm version
helm env
helm create chartName  -- create chart directory
helm package chartDir   -- package chart directory

helm search hub keyword    --  which lists helm charts from dozens of different repositories
helm search repo keyword    -- search the respositories that you have added to your local helm client(with helm repo add), this is done over local data and no public network connection is needed
helm push chart.tgz repoName    -- upload chart to chart registory
helm repo add xxx https://xxx
helm repo list
helm install <name> <name of the chart>
helm history jenkins
helm status jenkins
helm list  --check what's release installed




https://www.cnblogs.com/davis12/p/15469167.html

