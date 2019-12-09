# MavenCreateExecutableJarFile
=> Process to create executable jar file using maven 


use given below line to create jar file. you will get 2 jar file . one will be useful for self execution environment and another will be useful to provide third party services.


 <build>
        <plugins>
            <!-- Package as an executable jar/war -->
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <executions>
                  <execution>
                    <id>repackage</id>
                    <configuration>
                      <classifier>exec</classifier>
                    </configuration>
                  </execution>
                </executions>
            </plugin>
        </plugins>
    <finalName>email</finalName>
  </build>


To use the created jar file in another application ,

        <dependency>
            <groupId>mc</groupId>
            <artifactId>email</artifactId>
            <version>1.0</version>
            <type>jar</type>
            <scope>system</scope>
            <systemPath>${basedir}/src/main/webapp/WEB-INF/lib/email.jar</systemPath>
        </dependency>   




