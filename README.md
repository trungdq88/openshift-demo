# openshift-demo
Demo project for my openshift basic tutorial

# The video

Youtube: https://youtu.be/9qwIOZUy9tk (Vietnamese)

# Slide

Google Docs: https://docs.google.com/presentation/d/1SUNDQA1Ck1bMZ9cBBKfQ85UCzN1KpgbY2xsRE1VXTik/edit?usp=sharing

# Others

## Links
- Install Openshift client tool: https://developers.openshift.com/en/getting-started-overview.html
- Set up SSH key: https://developers.openshift.com/en/managing-remote-connection.html




## Create new Maven Java Web App:
```
mvn archetype:generate -DgroupId=com.dqt.guide.openshift -DartifactId=my-awesome-app -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false
```

## Openshift Maven profile
```xml
<profile>
    <!-- When built in OpenShift the 'openshift' profile will be used when
    invoking mvn. -->
    <!-- Use this profile for any OpenShift specific customization your app
    will need. -->
    <!-- By default that is to put the resulting archive into the 'webapps'
    folder. -->
    <!-- http://maven.apache.org/guides/mini/guide-building-for-different-environments.html -->
    <id>openshift</id>
    <build>
        <finalName>jbossews</finalName>
        <plugins>
            <plugin>
                <artifactId>maven-war-plugin</artifactId>
                <version>2.1.1</version>
                <configuration>
                    <outputDirectory>webapps</outputDirectory>
                    <warName>my-awesome-app</warName>
                </configuration>
            </plugin>
        </plugins>
    </build>
</profile>
```

