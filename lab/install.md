kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl port-forward svc/argocd-server -n argocd 8080:443 --address 0.0.0.0

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

Y2hmi0owGraEhyYM

Login via CLI 
Download and install the ArgoCD CLI tool suitable for your operating system and corresponding to your specific ArgoCD release version. More detailed installation instructions can be found in the CLI installation documentation. 

For Linux Fedora 42, you can install the latest (as of this publication) ArgoCD CLI using the following commands: 


curl -sSL -o argocd https://github.com/argoproj/argo-cd/releases/download/v2.13.2/argocd-linux-amd64
chmod +x argocd
sudo mv argocd /usr/local/bin/
argocd version --client

Using the username admin, the auto-generated password from above, and the port-forwarded service, log in to Argo CD accessible at https://localhost:8080. 
Command: 

argocd login localhost:8080 --username admin --password Y2hmi0owGraEhyYM 




