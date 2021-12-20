# Cloud Computing Tools

## Apache Brooklyn

Apache Brooklyn is a software for modeling, monitoring, and managing applications through autonomic blueprints across
cloud and non-cloud environments [[ref](https://brooklyn.apache.org/learnmore/theory.html)]. Brooklyn uses a YAML which
complies with CAMP syntax [[ref](http://docs.oasis-open.org/camp/camp-spec/v1.1/camp-spec-v1.1.html)].

Brooklyn blueprint can define application topology, application topology component and cloud or non-cloud location.
Blueprints can be added via web console or CLI.

Install Brooklyn CLI and start Brooklyn controller.

Create `my-location.brooklyn.yaml`:

```yaml
brooklyn.catalog:
  id: my-aws-eu-west-1-location
  name: 'My AWS EU West 1 location'
  itemType: location
  item:
    type: jclouds:aws-ec2
    brooklyn.config:
      region: eu-west-1
      identity: AWS_IDENTITY # replace
      credential: AWS_CREDENTIAL # replace
      loginUser: OS_LOGIN_USER # replace
      user: OS_USER # replace
      imageId: AWS_AMI_ID # replace
```

Add location to the Brooklyn catalog with the CLI:
```shell
$ br catalog add my-location.brooklyn.yaml
```

Create `my-application.brooklyn.yaml`:

```yaml
name: My Cloud Application
location: my-aws-eu-west-1-location
services:
# MySQL node
- type: org.apache.brooklyn.entity.database.mysql.MySqlNode
  id: mysql-node
  name: My Database
  brooklyn.config:
    datastore.creation.script.url: https://raw.githubusercontent.com/apache/brooklyn-library/master/examples/simple-web-cluster/src/main/resources/visitors-creation-script.sql
  pre.install.command: sudo apt-get install -y libncurses5 # Might be missing on some VMs
# Tomcat node
- type: org.apache.brooklyn.entity.webapp.tomcat.TomcatServer
  name: My Tomcat Server
  id: tomcat-node
  brooklyn.config:
    wars.root: https://repo1.maven.org/maven2/org/apache/brooklyn/example/brooklyn-example-hello-world-sql-webapp/0.12.0/brooklyn-example-hello-world-sql-webapp-0.12.0.war
    java.sysprops:
      brooklyn.example.db.url: $brooklyn:formatString("jdbc:%s%s?user=%s&password=%s", $brooklyn:component("mysql-node").attributeWhenReady("datastore.url"), "visitors", "brooklyn", "br00k11n")
```

Deploy application with the CLI:

```shell
$ br deploy my-application.brooklyn.yaml
```

Login into Brooklyn web console and inspect application deployment progress:

![brooklyn application](images/brooklyn-deployment-progress.png)

Indicators become green once application is successfully deployed:

![brooklyn application](images/brooklyn-application.png)

Navigate to sensors of the `my-tomcat-server` entity and find `main.uri`:

![brooklyn application](images/brooklyn-tomcat-entity.png)

Open link to see the Brooklyn sample web application:

![brooklyn application](images/brooklyn-tomcat-application.png)

Inspect with the CLI:

```shell
$ br locations
```

```shell
$ br applications
```

Try deploying same application topology from the composer:

![brooklyn application](images/brooklyn-yaml-editor.png)

![brooklyn application](images/brooklyn-composer.png)

See commercial version with a rich collection of features [[ref](https://docs.cloudsoft.io)], which helps to achieve
a high level of resilience, compliance and supports TOSCA standard
[[ref](https://docs.oasis-open.org/tosca/TOSCA-Simple-Profile-YAML/v1.3/os/TOSCA-Simple-Profile-YAML-v1.3-os.html)].