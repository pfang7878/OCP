helm charts:

commands:
helm search hub  which lists helm charts from dozens of different repositories
helm search repo   -- search the respositories that you have added to your local helm client(with helm repo add), this is done over local data and no public network connection is needed
helm repo add xxx https://xxx
helm repo list
helm install <name> <name of the chart>
helm status jenkins

