# Dependency Management with Gradle

Gradle fetches dependencies from an explicit list included in the `build.gradle` file.

```groovy
repositories {
    mavenCentral()
}
```

In a corporate environment, you might want to include your internal repository and delegate to it the mirroring of Maven Central in order to ensure a more controlled dependency resolving strategy.

```groovy
repositories {
    maven {
        url "https://corporate-repo.com/maven"
    }
}
```

Similarly, you might want to configure all Gradle plugins to be fetched through your corporate repository by applying the following changes to the `settings.gradle` file.

```groovy
pluginManagement {
    repositories {
        maven {
            url "https://corporate-repo.com/maven"
        }
    }
}
```

You can block any dynamic dependency resolution with the following configuration.

```groovy
configurations.configureEach {
    resolutionStrategy {
        failOnNonReproducibleResolution()
    }
}
```

You can lock all dependency versions by running the following command.

```shell
./gradlew dependencies --write-locks
```

And enforce it like this:

```groovy
dependencyLocking {
    lockAllConfigurations()
}
```

You can resolve and verify the checksums for all dependencies by running the following command.

```shell
./gradlew --write-verification-metadata sha256
```

If you also want to resolve and verify the signatures, you can update the `gradle/verification-metadata.xml` file as follows.

```xml
<configuration>
    <verify-metadata>true</verify-metadata>
    <verify-signatures>true</verify-signatures>
</configuration>
```
