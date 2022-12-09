### .bashrc file update

Update the below in the .bashrc file and then run . .bashrc

```
alias k=kubectl                         # will already be pre-configured

alias kx='f() { [ "$1" ] && kubectl config use-context $1 || kubectl config current-context ; } ; f'
alias kn='f() { [ "$1" ] && kubectl config set-context --current --namespace $1 || kubectl config view --minify | grep namespace | cut -d" " -f6 ; } ; f'

export do="--dry-run=client -o yaml"    # k create deploy nginx --image=nginx $do

export now="--force --grace-period 0"   # k delete pod x $now
```

Run a temporaray pod and check service status
```
kubectl run temp --image=nginx:alpine --restart=Never --rm -it -- curl <service>.<namespace>:<port>

for example - 
k run temp --restart=Never --rm --image=nginx:alpine -i -- curl http://project-plt-6cc-svc.pluto:3333
```
