Если не будет возможности склонировать репозиторий по ссылке, то воспользоваться файлом template.zip

https://github.com/BND86/template

Данный репозиторий - это шаблон проекта с настроенным gradle, для установки необходимых зависимостей для всех типов практических заданий.

Большая часть необходимых библиотек загружается через `spring-boot-starter`, помимо этого есть драйвер для PostgreSQL и JUnit для тестирования.

Версии библиотек работают с Java 21.

В папке `/lib` находятся `.jar` файлы для всех зависимостей, на случай отсутсвия интернет соединения.
Чтобы использовать их, в файле buiild.gradle.kts есть данная строка (по умолчанию закомментирована):
```Kotlin
implementation(fileTree(mapOf("dir" to "lib", "include" to listOf("*.jar"))))
```

Полный список зависимостей в данном проекте:

```
+--- org.springframework.boot:spring-boot-starter-data-jpa -> 3.3.2
|    +--- org.springframework.boot:spring-boot-starter-aop:3.3.2
|    |    +--- org.springframework.boot:spring-boot-starter:3.3.2
|    |    |    +--- org.springframework.boot:spring-boot:3.3.2
|    |    |    |    +--- org.springframework:spring-core:6.1.11
|    |    |    |    |    \--- org.springframework:spring-jcl:6.1.11
|    |    |    |    \--- org.springframework:spring-context:6.1.11
|    |    |    |         +--- org.springframework:spring-aop:6.1.11
|    |    |    |         |    +--- org.springframework:spring-beans:6.1.11
|    |    |    |         |    |    \--- org.springframework:spring-core:6.1.11 (*)
|    |    |    |         |    \--- org.springframework:spring-core:6.1.11 (*)
|    |    |    |         +--- org.springframework:spring-beans:6.1.11 (*)
|    |    |    |         +--- org.springframework:spring-core:6.1.11 (*)
|    |    |    |         +--- org.springframework:spring-expression:6.1.11
|    |    |    |         |    \--- org.springframework:spring-core:6.1.11 (*)
|    |    |    |         \--- io.micrometer:micrometer-observation:1.12.8 -> 1.13.2
|    |    |    |              \--- io.micrometer:micrometer-commons:1.13.2
|    |    |    +--- org.springframework.boot:spring-boot-autoconfigure:3.3.2
|    |    |    |    \--- org.springframework.boot:spring-boot:3.3.2 (*)
|    |    |    +--- org.springframework.boot:spring-boot-starter-logging:3.3.2
|    |    |    |    +--- ch.qos.logback:logback-classic:1.5.6
|    |    |    |    |    +--- ch.qos.logback:logback-core:1.5.6
|    |    |    |    |    \--- org.slf4j:slf4j-api:2.0.13
|    |    |    |    +--- org.apache.logging.log4j:log4j-to-slf4j:2.23.1
|    |    |    |    |    +--- org.apache.logging.log4j:log4j-api:2.23.1
|    |    |    |    |    \--- org.slf4j:slf4j-api:2.0.9 -> 2.0.13
|    |    |    |    \--- org.slf4j:jul-to-slf4j:2.0.13
|    |    |    |         \--- org.slf4j:slf4j-api:2.0.13
|    |    |    +--- jakarta.annotation:jakarta.annotation-api:2.1.1
|    |    |    +--- org.springframework:spring-core:6.1.11 (*)
|    |    |    \--- org.yaml:snakeyaml:2.2
|    |    +--- org.springframework:spring-aop:6.1.11 (*)
|    |    \--- org.aspectj:aspectjweaver:1.9.22.1
|    +--- org.springframework.boot:spring-boot-starter-jdbc:3.3.2
|    |    +--- org.springframework.boot:spring-boot-starter:3.3.2 (*)
|    |    +--- com.zaxxer:HikariCP:5.1.0
|    |    |    \--- org.slf4j:slf4j-api:1.7.36 -> 2.0.13
|    |    \--- org.springframework:spring-jdbc:6.1.11
|    |         +--- org.springframework:spring-beans:6.1.11 (*)
|    |         +--- org.springframework:spring-core:6.1.11 (*)
|    |         \--- org.springframework:spring-tx:6.1.11
|    |              +--- org.springframework:spring-beans:6.1.11 (*)
|    |              \--- org.springframework:spring-core:6.1.11 (*)
|    +--- org.hibernate.orm:hibernate-core:6.5.2.Final
|    |    +--- jakarta.persistence:jakarta.persistence-api:3.1.0
|    |    +--- jakarta.transaction:jakarta.transaction-api:2.0.1
|    |    +--- org.jboss.logging:jboss-logging:3.5.0.Final -> 3.5.3.Final
|    |    +--- org.hibernate.common:hibernate-commons-annotations:6.0.6.Final
|    |    +--- io.smallrye:jandex:3.1.2
|    |    +--- com.fasterxml:classmate:1.5.1 -> 1.7.0
|    |    +--- net.bytebuddy:byte-buddy:1.14.15 -> 1.14.18
|    |    +--- jakarta.xml.bind:jakarta.xml.bind-api:4.0.0 -> 4.0.2
|    |    |    \--- jakarta.activation:jakarta.activation-api:2.1.3
|    |    +--- org.glassfish.jaxb:jaxb-runtime:4.0.2 -> 4.0.5
|    |    |    \--- org.glassfish.jaxb:jaxb-core:4.0.5
|    |    |         +--- jakarta.xml.bind:jakarta.xml.bind-api:4.0.2 (*)
|    |    |         +--- jakarta.activation:jakarta.activation-api:2.1.3
|    |    |         +--- org.eclipse.angus:angus-activation:2.0.2
|    |    |         |    \--- jakarta.activation:jakarta.activation-api:2.1.3
|    |    |         +--- org.glassfish.jaxb:txw2:4.0.5
|    |    |         \--- com.sun.istack:istack-commons-runtime:4.1.2
|    |    +--- jakarta.inject:jakarta.inject-api:2.0.1
|    |    \--- org.antlr:antlr4-runtime:4.13.0
|    +--- org.springframework.data:spring-data-jpa:3.3.2
|    |    +--- org.springframework.data:spring-data-commons:3.3.2
|    |    |    +--- org.springframework:spring-core:6.1.9 -> 6.1.11 (*)
|    |    |    +--- org.springframework:spring-beans:6.1.9 -> 6.1.11 (*)
|    |    |    \--- org.slf4j:slf4j-api:2.0.2 -> 2.0.13
|    |    +--- org.springframework:spring-orm:6.1.9 -> 6.1.11
|    |    |    +--- org.springframework:spring-beans:6.1.11 (*)
|    |    |    +--- org.springframework:spring-core:6.1.11 (*)
|    |    |    +--- org.springframework:spring-jdbc:6.1.11 (*)
|    |    |    \--- org.springframework:spring-tx:6.1.11 (*)
|    |    +--- org.springframework:spring-context:6.1.9 -> 6.1.11 (*)
|    |    +--- org.springframework:spring-aop:6.1.9 -> 6.1.11 (*)
|    |    +--- org.springframework:spring-tx:6.1.9 -> 6.1.11 (*)
|    |    +--- org.springframework:spring-beans:6.1.9 -> 6.1.11 (*)
|    |    +--- org.springframework:spring-core:6.1.9 -> 6.1.11 (*)
|    |    +--- org.antlr:antlr4-runtime:4.13.0
|    |    +--- jakarta.annotation:jakarta.annotation-api:2.0.0 -> 2.1.1
|    |    \--- org.slf4j:slf4j-api:2.0.2 -> 2.0.13
|    \--- org.springframework:spring-aspects:6.1.11
|         \--- org.aspectj:aspectjweaver:1.9.22.1
+--- org.springframework.boot:spring-boot-starter-web -> 3.3.2
|    +--- org.springframework.boot:spring-boot-starter:3.3.2 (*)
|    +--- org.springframework.boot:spring-boot-starter-json:3.3.2
|    |    +--- org.springframework.boot:spring-boot-starter:3.3.2 (*)
|    |    +--- org.springframework:spring-web:6.1.11
|    |    |    +--- org.springframework:spring-beans:6.1.11 (*)
|    |    |    +--- org.springframework:spring-core:6.1.11 (*)
|    |    |    \--- io.micrometer:micrometer-observation:1.12.8 -> 1.13.2 (*)
|    |    +--- com.fasterxml.jackson.core:jackson-databind:2.17.2
|    |    |    +--- com.fasterxml.jackson.core:jackson-annotations:2.17.2
|    |    |    |    \--- com.fasterxml.jackson:jackson-bom:2.17.2
|    |    |    |         +--- com.fasterxml.jackson.core:jackson-annotations:2.17.2 (c)
|    |    |    |         +--- com.fasterxml.jackson.core:jackson-core:2.17.2 (c)
|    |    |    |         +--- com.fasterxml.jackson.core:jackson-databind:2.17.2 (c)
|    |    |    |         +--- com.fasterxml.jackson.datatype:jackson-datatype-jdk8:2.17.2 (c)
|    |    |    |         +--- com.fasterxml.jackson.datatype:jackson-datatype-jsr310:2.17.2 (c)
|    |    |    |         \--- com.fasterxml.jackson.module:jackson-module-parameter-names:2.17.2 (c)
|    |    |    +--- com.fasterxml.jackson.core:jackson-core:2.17.2
|    |    |    |    \--- com.fasterxml.jackson:jackson-bom:2.17.2 (*)
|    |    |    \--- com.fasterxml.jackson:jackson-bom:2.17.2 (*)
|    |    +--- com.fasterxml.jackson.datatype:jackson-datatype-jdk8:2.17.2
|    |    |    +--- com.fasterxml.jackson.core:jackson-core:2.17.2 (*)
|    |    |    +--- com.fasterxml.jackson.core:jackson-databind:2.17.2 (*)
|    |    |    \--- com.fasterxml.jackson:jackson-bom:2.17.2 (*)
|    |    +--- com.fasterxml.jackson.datatype:jackson-datatype-jsr310:2.17.2
|    |    |    +--- com.fasterxml.jackson.core:jackson-annotations:2.17.2 (*)
|    |    |    +--- com.fasterxml.jackson.core:jackson-core:2.17.2 (*)
|    |    |    +--- com.fasterxml.jackson.core:jackson-databind:2.17.2 (*)
|    |    |    \--- com.fasterxml.jackson:jackson-bom:2.17.2 (*)
|    |    \--- com.fasterxml.jackson.module:jackson-module-parameter-names:2.17.2
|    |         +--- com.fasterxml.jackson.core:jackson-core:2.17.2 (*)
|    |         +--- com.fasterxml.jackson.core:jackson-databind:2.17.2 (*)
|    |         \--- com.fasterxml.jackson:jackson-bom:2.17.2 (*)
|    +--- org.springframework.boot:spring-boot-starter-tomcat:3.3.2
|    |    +--- jakarta.annotation:jakarta.annotation-api:2.1.1
|    |    +--- org.apache.tomcat.embed:tomcat-embed-core:10.1.26
|    |    +--- org.apache.tomcat.embed:tomcat-embed-el:10.1.26
|    |    \--- org.apache.tomcat.embed:tomcat-embed-websocket:10.1.26
|    |         \--- org.apache.tomcat.embed:tomcat-embed-core:10.1.26
|    +--- org.springframework:spring-web:6.1.11 (*)
|    \--- org.springframework:spring-webmvc:6.1.11
|         +--- org.springframework:spring-aop:6.1.11 (*)
|         +--- org.springframework:spring-beans:6.1.11 (*)
|         +--- org.springframework:spring-context:6.1.11 (*)
|         +--- org.springframework:spring-core:6.1.11 (*)
|         +--- org.springframework:spring-expression:6.1.11 (*)
|         \--- org.springframework:spring-web:6.1.11 (*)
+--- org.springframework.boot:spring-boot-starter-validation -> 3.3.2
|    +--- org.springframework.boot:spring-boot-starter:3.3.2 (*)
|    +--- org.apache.tomcat.embed:tomcat-embed-el:10.1.26
|    \--- org.hibernate.validator:hibernate-validator:8.0.1.Final
|         +--- jakarta.validation:jakarta.validation-api:3.0.2
|         +--- org.jboss.logging:jboss-logging:3.4.3.Final -> 3.5.3.Final
|         \--- com.fasterxml:classmate:1.5.1 -> 1.7.0
+--- org.apache.commons:commons-csv:1.13.0
|    +--- commons-io:commons-io:2.18.0
|    \--- commons-codec:commons-codec:1.17.2 -> 1.16.1
+--- org.postgresql:postgresql -> 42.7.3
|    \--- org.checkerframework:checker-qual:3.42.0
+--- org.springframework.boot:spring-boot-starter-test -> 3.3.2
|    +--- org.springframework.boot:spring-boot-starter:3.3.2 (*)
|    +--- org.springframework.boot:spring-boot-test:3.3.2
|    |    +--- org.springframework.boot:spring-boot:3.3.2 (*)
|    |    \--- org.springframework:spring-test:6.1.11
|    |         \--- org.springframework:spring-core:6.1.11 (*)
|    +--- org.springframework.boot:spring-boot-test-autoconfigure:3.3.2
|    |    +--- org.springframework.boot:spring-boot:3.3.2 (*)
|    |    +--- org.springframework.boot:spring-boot-test:3.3.2 (*)
|    |    \--- org.springframework.boot:spring-boot-autoconfigure:3.3.2 (*)
|    +--- com.jayway.jsonpath:json-path:2.9.0
|    |    +--- net.minidev:json-smart:2.5.0 -> 2.5.1
|    |    |    \--- net.minidev:accessors-smart:2.5.1
|    |    |         \--- org.ow2.asm:asm:9.6
|    |    \--- org.slf4j:slf4j-api:2.0.11 -> 2.0.13
|    +--- jakarta.xml.bind:jakarta.xml.bind-api:4.0.2 (*)
|    +--- net.minidev:json-smart:2.5.1 (*)
|    +--- org.assertj:assertj-core:3.25.3
|    |    \--- net.bytebuddy:byte-buddy:1.14.11 -> 1.14.18
|    +--- org.awaitility:awaitility:4.2.1
|    |    \--- org.hamcrest:hamcrest:2.1 -> 2.2
|    +--- org.hamcrest:hamcrest:2.2
|    +--- org.junit.jupiter:junit-jupiter:5.10.3
|    |    +--- org.junit:junit-bom:5.10.3
|    |    |    +--- org.junit.jupiter:junit-jupiter:5.10.3 (c)
|    |    |    +--- org.junit.jupiter:junit-jupiter-api:5.10.3 (c)
|    |    |    +--- org.junit.jupiter:junit-jupiter-engine:5.10.3 (c)
|    |    |    +--- org.junit.jupiter:junit-jupiter-params:5.10.3 (c)
|    |    |    +--- org.junit.platform:junit-platform-engine:1.10.3 (c)
|    |    |    +--- org.junit.platform:junit-platform-launcher:1.10.3 (c)
|    |    |    \--- org.junit.platform:junit-platform-commons:1.10.3 (c)
|    |    +--- org.junit.jupiter:junit-jupiter-api:5.10.3
|    |    |    +--- org.junit:junit-bom:5.10.3 (*)
|    |    |    +--- org.opentest4j:opentest4j:1.3.0
|    |    |    \--- org.junit.platform:junit-platform-commons:1.10.3
|    |    |         \--- org.junit:junit-bom:5.10.3 (*)
|    |    +--- org.junit.jupiter:junit-jupiter-params:5.10.3
|    |    |    +--- org.junit:junit-bom:5.10.3 (*)
|    |    |    \--- org.junit.jupiter:junit-jupiter-api:5.10.3 (*)
|    |    \--- org.junit.jupiter:junit-jupiter-engine:5.10.3
|    |         +--- org.junit:junit-bom:5.10.3 (*)
|    |         +--- org.junit.platform:junit-platform-engine:1.10.3
|    |         |    +--- org.junit:junit-bom:5.10.3 (*)
|    |         |    +--- org.opentest4j:opentest4j:1.3.0
|    |         |    \--- org.junit.platform:junit-platform-commons:1.10.3 (*)
|    |         \--- org.junit.jupiter:junit-jupiter-api:5.10.3 (*)
|    +--- org.mockito:mockito-core:5.11.0
|    |    +--- net.bytebuddy:byte-buddy:1.14.12 -> 1.14.18
|    |    +--- net.bytebuddy:byte-buddy-agent:1.14.12 -> 1.14.18
|    |    \--- org.objenesis:objenesis:3.3
|    +--- org.mockito:mockito-junit-jupiter:5.11.0
|    |    +--- org.mockito:mockito-core:5.11.0 (*)
|    |    \--- org.junit.jupiter:junit-jupiter-api:5.10.2 -> 5.10.3 (*)
|    +--- org.skyscreamer:jsonassert:1.5.3
|    |    \--- com.vaadin.external.google:android-json:0.0.20131108.vaadin1
|    +--- org.springframework:spring-core:6.1.11 (*)
|    +--- org.springframework:spring-test:6.1.11 (*)
|    \--- org.xmlunit:xmlunit-core:2.9.1
\--- org.junit.platform:junit-platform-launcher -> 1.10.3
     +--- org.junit:junit-bom:5.10.3 (*)
     \--- org.junit.platform:junit-platform-engine:1.10.3 (*)
```
