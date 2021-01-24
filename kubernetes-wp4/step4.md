# Explicit > Implicit

So far with ´kubectl run´ we have implicitly started a container
If we want to start explicitly we need a yaml file
This is an easy way how to generate one:

 `kubectl run secondtry --dry-run=client --image=alpine ping google.com -o yaml > secondtry.yaml`{{execute}}

To deploy it you type:

  `kubectl create -f secondtry.yaml`{{execute}}


  sudo curl -L -o /usr/local/bin/stern \
   https://github.com/wercker/stern/releases/download/1.10.0/stern_linux_amd64
sudo chmod +x /usr/local/bin/stern