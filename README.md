Deploying Mongodb and MongoExpress

First I create a Mongodb Pod and to talk to talk to the Pod, I need a service, so a service i s created alongside the Pod

No external requests are allowed to the pod, only pod in cluster can communicate'

Next a MongoExpress was created and a Mongodb url was needed so that the MongoExpress can connect to it

Username and password will be created so that it can authenticate to the DataBase, so this is where the "Environmental Variables" come in

Next a config map that contains the database URL was created as well as a secret that contains the credentials and both was referenced inside the deployment file

Because i needed MongoExpress to be accessible through browser, i created an external service so that external request can talk to it

## REQUEST FLOW

BROWSER >>>>> MONGOEXPRESS EXTERNAL SERVICE >>>> MONGOEXPRESS POD >>>> MONGODB INTERNAL SERVICE >>>> MONGODB POD