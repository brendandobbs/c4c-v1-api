1. Goto the C4H Cockpit (https://cockpit.cx.cloud.sap) and get the token URL for the C4C application 
2. Download the client certificate using the one click integration script (change URL below)

```
./one-click-integration-script.sh -u https://connector-service.extend.cx.cloud.sap/v1/applications/signingRequests/info?token=xxxxxxxx 
```
3. Update targetUrl, specificationUrl, credentials and specificationCredentials in c4c-v1-api.json to match your C4C tenant 

4. Execute the following command (replace 'c4f-demo3' with the value for your cluster
```
curl -X POST -d @c4c-v1-api.json https://gateway.c4f-demo3.cluster.extend.cx.cloud.sap/c4c-test2/v1/metadata/services --cert generated.crt --key generated.key -k```
