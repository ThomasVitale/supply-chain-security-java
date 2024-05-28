# Dependency Management with Maven

Maven fetches dependencies from a cascaded sequence of `pom.xml` file. By default, every Maven projects inherits from a super-pom that configures access to the Maven Central repository.

If you're curious about all the default configuration applied by the super-pom, run this command.

```shell
./mvnw help:effective-pom
```

In a corporate environment, you might want to include your internal repository and delegate to it the mirroring of Maven Central in order to ensure a more controlled dependency resolving strategy.

```xml
<repositories>
    <repository>
        <id>corporate-repo</id>
        <url>corporate-repo.com/maven</url>
    </repository>
</repositories>
```

But remember to disable the Maven Central repository which is included by default.

```xml
<repositories>
    <repository>
        <id>central</id>
        <releases>
            <enabled>false</enabled>
        </releases>
    </repository>
</repositories>
```

Similarly, you might want to configure all Maven plugins to be fetched through your corporate repository by applying the following changes to the `pom.xml` file.

```xml
<pluginRepositories>
    <pluginRepository>
        <id>corporate-repo</id>
        <url>corporate-repo.com/maven</url>
    </pluginRepository>
</pluginRepositories>
```

But remember to disable the Maven Central repository which is included by default.

```xml
<pluginRepositories>
    <pluginRepository>
        <id>central</id>
        <releases>
            <enabled>false</enabled>
        </releases>
    </pluginRepository>
</pluginRepositories>
```

You can lock all dependency versions by using the [dependency-lock-maven-plugin](https://github.com/vandmo/dependency-lock-maven-plugin).

```shell
./mvnw se.vandmo:dependency-lock-maven-plugin:lock
```
