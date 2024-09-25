# OCP
Redhat OpenShift Container Platform



commands:
oc get pods -n openshift-console | grep console      check web console is avalable
oc get routes console -n openshift-console -o jsonpath='{"https://"}{.spec.host}{"\n"}'      find route to web console
oc login -u developer -p developer        
oc login --username= developer --server=https://xxx  --insecure-skip-tls-verify=true
oc project xxxx
oc get projects
oc whoami
oc whoami --show-server        verify the server you logged into 

oc login --username user1 --password user1            creatting a new user
rolebinding:
under project -- project access -- role binding -- creat rolebinding -- name,namespace,rolename,user --  
oc new-project yourproject            create a new project
oc adm policy add-role-to-user view developer -n myproject
oc login -u developer -p developer

switching users between accounts:
oc login --useranme developer            switching between users without password, only first time need password on same machine
oc login --token=<token> --server=https://api.sandbox-m2.ll9k.p1.openshiftapps.com:6443                    switching between OCP clusters
oc whoami --show-context                view current context
oc whoami --show-server                  check server you logged into
oc config get-clusters                  list all OCP clusters you have logged into
oc config get-contexts                  list all context have ever been created



install ansible operator:
oc new-project dev-game-app
install ansible automation platform to namespace aap
oc get operators
oc get pods -n aap
create an instance of automation controller named ansible
to access UI of ansible automation platform:
export SA_SECRET=ansible
oc get route -n aap | grep $(echo ${SA_SECRET}) | awk '{print$2}'
copy the url to broswer
username is admin
oc get secret $SA_SECRET-admin-password -o jsonpath='{.data.password}' -n aap | base64 --decode       Get password
setup subscrib






TS:
oc get sa -n uat-admin002
oc get sa jenkins -n uat-admin002
oc get sa jenkins -n uat-admin002 -oyaml
oc get sa -n cicd
oc get sa jenkins -n cicd -oyaml
oc get sa secrect -n uat-admon002
oc get sa jenkins -n uat-admin002 -oyaml > /tmp/jenkinssa.yaml
oc edit sa jenkins -n uat-admin002
oc get svc -n cicd
oc get svc -n cicd jenkins -oyaml
oc get svc jenkins -n uat-admin002 > /tmp/svc.yaml
oc edit svc jenkins -n uat-admin002
oc get all
oc get svc
oc get svc jenkins-jnlp
oc get svc jenkins-jnlp -oyaml > /tmp/jnlp.yaml
oc get all
oc delete svc jenkins jenkins-jnlp
oc delete route jenkins
oc get build -oyaml
