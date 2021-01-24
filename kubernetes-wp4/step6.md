# Let's deploy a webapp declaratively

Create a new deployment yaml

<pre class="file" data-filename="myapp.yaml" data-target="replace">
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp
        image: docker.io/alexhiesch/simple-http-server
        resources:
          limits:
            memory: "128Mi"
            cpu: "500m"
        ports:
        - name: myapp
          containerPort: 80

---
apiVersion: v1
kind: Service
metadata:
  name: myapp
spec:
  type: NodePort
  selector:
    app: myapp
  ports:
    - name: myapp
      port: 80
      targetPort: 80
      nodePort: 30000
</pre>


Deploy it
`kubectl apply -f myapp.yaml`{{execute}}

Check its status
`kubectl get all`{{execute}}

Open up the webpage

[Try it out here](https://[[HOST_SUBDOMAIN]]-30000-[[KATACODA_HOST]].environments.katacoda.com)
