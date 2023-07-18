## Steps to set up a DataPower docker image (the image that I am using is 10.0.5.6)

### Step 1: Get the image
Follow this link https://www.ibm.com/support/pages/how-get-datapower-docker-images-past-versions-v10030v10014v20184117

### Step 2: Get the entitlement key (or use the limited edition)
Follow this for more information https://www.ibm.com/docs/en/datapower-operator/1.7?topic=features-entitled-registry
Set up the k8s secret using oc or kubectl:
```
kubectl create secret docker-registry ibm-entitlement-key --docker-username=cp --docker-password=eyJ0e...IUzI1NiJ9.eyJpc3MiOiJIjM...ZTE1OWI5NGY3In0.CEdsxb.....whP9A --docker-server=cp.icr.io
```
### Step 3: Pull down the image
```
docker pull icr.io/cpopen/datapower/datapower-limited:10.5.0.6
```

### Run
```
docker run -it \
  -v $PWD/config:/drouter/config \
  -v $PWD/local:/drouter/local \
  -e DATAPOWER_ACCEPT_LICENSE=true \
  -e DATAPOWER_INTERACTIVE=true \
  -p 9090:9090   -p 9022:22   -p 5554:5554 \
  -p 8000-8080:8000-8080 \
  --name idg \
  icr.io/cpopen/datapower/datapower-limited:10.5.0.6
```

### Login, enable the WebGUI
```
login: admin
Password: ***** (admin)
config
web-mgmt 0 9090
```

### Opitonal set idle timeout to 0 (never idle the session)
```
idg(config)# web-mgmt
idg(config web-mgmt)# idle-timeout 0
idg(config web-mgmt)# exit
idg(config)# write
Overwrite previously saved configuration? Yes/No [y/n]: y
Configuration saved successfully.
```

You are ready to go (have fun)
<img width="795" alt="image" src="https://github.com/shiup/howto/assets/24717424/581bee11-0b0f-42f7-a62f-9fcc5816da90">


