# MAVEN

## Init New Project
Provide all settings - no questions asked
`$ mvn archetype:generate -B -DgroupId=.com.hss -DartifactId=aws-transforms`

## Build Lifecycle
clean
default
site

## Lifecycle Phases
compile
test
package
install

## SHADE EXECUTABLE
Add build setup to pom.xml
```
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-shade-plugin</artifactId>
        <version>2.4.3</version>
        <executions>
          <execution>
            <phase>package</phase>
            <goals>
              <goal>shade</goal>
            </goals>
            <configuration>
              <transformers>
                <transformer implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
                  <mainClass>com.hss</mainClass>
                </transformer>
              </transformers>
            </configuration>
          </execution>
        </executions>
      </plugin>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <configuration>
          <source>1.8</source>
          <target>1.8</target>
        </configuration>
      </plugin>
    </plugins>
  </build>
```

## Create Executable
(https://maven.apache.org/plugins/maven-shade-plugin/usage.html)
```
$ add shade plugin to pom.xml
$ mvn shade
```
