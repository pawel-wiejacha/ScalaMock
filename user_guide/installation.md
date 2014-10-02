# Installation

## Packages 

You can download ScalaMock from [Sonatype](https://oss.sonatype.org/content/repositories/releases/org/scalamock/).

## Sources

You can find ScalaMock source code and repository on [Github](https://github.com/paulbutcher/ScalaMock)

## sbt projects

* To use ScalaMock in [sbt](http://www.scala-sbt.org/) with [ScalaTest](http://www.scalatest.org/) add the following to your project file:
  ```scala
  libraryDependencies += "org.scalamock" %% "scalamock-scalatest-support" % "3.1.4" % "test"
  ```

* To use ScalaMock with [Specs2](http://etorreborre.github.com/specs2/):
  ```scala
  libraryDependencies += "org.scalamock" %% "scalamock-specs2-support" % "3.1.4" % "test"
  ```

## Maven projects

To include ScalaMock in your Maven project add the following to your pom.xml
```xml
<dependency>
    <groupId>org.scalamock</groupId>
    <artifactId>scalamock-scalatest-support_2.11</artifactId> <!-- or scalamock-specs2-support_2.11 -->
    <version>3.1.4</version>
    <scope>test</scope>
</dependency>
```


