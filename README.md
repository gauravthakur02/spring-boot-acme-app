# spring-boot-acme-app
This is a helm chart of acme spring-boot application.

## <ins>Steps to install this "acme-spring-boot" application</ins>:
1. Clone the repository.
2. Change directory to "/spring-boot-acme-app/acme/"
3. To check the structure of the helm chart: 
```ShellSession
tree ./acme
```
4. In the "Chart.yaml" the description of the helm chart is present.
5. In the "values.yaml" the values/variables is present.
6. In the "templates" directory there are templates like:
  - deployment.yaml
  - hpa.yaml
  - ingress.yaml
  - service.yaml
  - serviceaccount.yaml
7. In "values.yaml" I have changed the "**image**" as "repository: msathepivotal/myfirst-boot-on-docker" and "tag: latest". Also in "**service**" as "LoadBalancer" and "ContainerPort" to 8080.
8. In "deploymemt.yaml" I have changed the "specs -> containers -> ports -> contianerPort" to "{{ .Values.containerPort }}" 
9. No need to change any thing in "services.yaml"
10. Test the helm chart for errors:
```ShellSession
helm lint ./acme
```
11. Do a dry-run to see if there aren't any issues when doing deployment using the helm chart ("acme-stocks" is the release name):
```ShellSession
helm install --dry-run acme-stocks ./acme
```
12. Do the deployment using this helm chart:
 ```ShellSession
 helm install acme-stocks ./acme
 ```
 13. To delete the helm deployment:
 ```ShellSession
 helm delete acme-stocks
 ```
 
