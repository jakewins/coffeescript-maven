# Coffeescript-maven

Coffeescript maven is a maven plugin that uses JCoffeescript 
to compile CoffeeScript 1.0 as part of your maven build.

### Usage

Coffeescript-maven is not yet in maven central, so for now you have to install
it manually:

    git clone git://github.com/jakewins/coffeescript-maven.git
    cd coffeescript-maven
    mvn clean install

Than, add the plugin to your pom:

    <plugins> 
      ..
      <plugin>
        <groupId>com.voltvoodoo</groupId>
        <artifactId>coffeescript-maven</artifactId>
        <version>1.0-SNAPSHOT</version>
        <executions>
          <execution>
            <goals>
              <goal>compile</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>

### Goals

Coffeescript-maven has one goal, "compile", by default attached to the
"compile" maven phase. The compile goal finds your .coffee files, runs
the coffeescript compiler on them, and puts the output in your output
directory (see below).

### Default settings

Coffeescript-maven will by default look for coffeescript files (**/*.coffee) 
recursively in ${basedir}/src/main/coffeescript, and output the compiled js files 
into ${project.build.outputDirectory}.

You can change these two settings by configuration:
  
    <plugins> 
      ..
      <plugin>
        <groupId>com.voltvoodoo</groupId>
        <artifactId>coffeescript-maven</artifactId>
        <version>1.0-SNAPSHOT</version>
        <executions>
          <execution>
            <goals>
              <goal>compile</goal>
            </goals>
          </execution>
        </executions>
        <configuration>
          <sourceDir>${basedir}/my/awesome/directory</sourceDir>
          <outputDir>${basedir}/src/main/webapp/js</outputDir>
        </configuration>
      </plugin>
    </plugins>