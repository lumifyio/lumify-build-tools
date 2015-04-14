# Lumify Build Tools

Tools and configuration files used by [Lumify](https://github.com/lumifyio/lumify) projects
during the build process. This project is typically included as a dependency for a Maven
plugin.

#### Example Plugin Definition (in pom.xml)

```xml
<plugin>
    <groupId>com.shankyank.mojo</groupId>
    <artifactId>template-resgen-maven-plugin</artifactId>
    <version>${plugin.template.resgen.version}</version>
    <executions>
        <execution>
            <id>gen-build-properties</id>
            <goals>
                <goal>generate-resource</goal>
            </goals>
            <configuration>
                <template>lumify/lumify-build.properties</template>
                <outputFileName>META-INF/lumify/${project.artifactId}-build.properties</outputFileName>
                <templateEncoding>UTF-8</templateEncoding>
                <outputEncoding>UTF-8</outputEncoding>
            </configuration>
        </execution>
    </executions>
    <dependencies>
        <dependency>
            <groupId>io.lumify</groupId>
            <artifactId>lumify-build-tools</artifactId>
            <version>1.0</version>
        </dependency>
    </dependencies>
</plugin>
```
