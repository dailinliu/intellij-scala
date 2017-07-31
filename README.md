[![TC Build Status](https://teamcity.jetbrains.com/app/rest/builds/buildType:(id:Scala_Tests)/statusIcon.svg)](https://teamcity.jetbrains.com/viewType.html?buildTypeId=Scala_Tests&guest=1)
[![Travis Build Status](https://travis-ci.org/JetBrains/intellij-scala.svg)](https://travis-ci.org/JetBrains/intellij-scala) 
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/JetBrains/intellij-scala)


# Scala Plugin for IntelliJ IDEA

Plugin that implements Scala, SBT, Play 2, SSP and Hocon support in IntelliJ IDEA.

## General information

- To get information about how to install and use this plugin in IDEA, please
  use [IntelliJ IDEA online help](https://www.jetbrains.com/idea/help/scala.html).

- If you have any question about the Scala plugin, we'd be glad to answer it in [our
  developer community](https://devnet.jetbrains.com/community/idea/scala).

- If you found a bug, please report it on [our issue
  tracker](https://youtrack.jetbrains.com/issues/SCL#newissue).

- If you want to contribute, please see our [intro to the Scala plugin
  internals](http://blog.jetbrains.com/scala/2016/04/21/how-to-contribute-to-intellij-scala-plugin/).

## Setting up the project

In order to take part in Scala plugin development, you need to:

1. Install IntelliJ IDEA 2017.1 or higher with a compatible version of Scala plugin

2. Fork this repository and clone it to your computer

  ```
  $ git clone https://github.com/JetBrains/intellij-scala.git
  ```

3. Open IntelliJ IDEA, select `File -> New -> Project from existing sources`, point to
the directory where Scala plugin repository is and then import it as SBT project.

4. When importing is finished, in order to get artifacts and run configurations for IDEA project,
go to the Scala plugin repo directory and run

  ```
  $ git checkout .idea
  ```


5. Open the SBT options (`Preferences -> Build, Execution, Deployment -> SBT`)

  - select `Use SBT shell for build and import`
  - in `Global SBT settings -> JVM Options -> Maximum heap size`, enter at least `2048`

6. Select the IDEA run configuration and select the `Run` or `Debug` button to build and start a development version
of IDEA with the Scala plugin.

## Tests

To run tests properly, the plugin needs to be packaged.
On the sbt shell:

1. `packagePluginCommunity`
2. `runFastTests`

The "fast tests" can take over an hour. To get a quick feedback on project health, run the "typeInference tests"

    > testOnly org.jetbrains.plugins.scala.lang.typeInference.*
    
## Travis CI

The project is configured to build and run the typeInference tests with Travis CI, which you can enable in your forks.
The full test suite can't currently be run because Travis doesn't allow builds to take that long.
