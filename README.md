# kubernetes-mssql
Project kubernetes mssql 2019

# pwd encode base64 
Username: sa
Password: P@ssw0rd

# Step 1: create secret
kubectl apply -f mssql-secret.yml

# Step 2: create persite volume
kubectl apply -f mssql-persist.yml

# Step 3: deploy the pod 
kubectl apply -f mssql-deployment.yml

# Step 4: applay port forward
kubectl port-forward service/mssql-service 30090:1433

# Step 5: delete pod and service
kubectl delete -f mssql-deployment.yml
kubectl delete -f mssql-secret.yml
kubectl delete -f mssql-persist.yml