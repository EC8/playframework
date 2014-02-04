<!--- Copyright (C) 2009-2013 Typesafe Inc. <http://www.typesafe.com> -->
# 새로운 어플리케이션 생성

## Typesafe Activator 를 이용한 새 어플리케이션 생성하기

[Typesafe Activator](http://typesafe.com/activator) 를 이용해 Play 프레임웍을 설치했다면, [여기](http://typesafe.com/platform/getstarted) 있는 지시를 보고 어떻게 새로운 어플리케이션을 생성하는지 따라해보도록 한다.

## Play 독립 배포판으로 새로운 어플리케이션 생성하기

Play 독립 배포판에는 `play` 라 불리는 새 어플리케이션을 쉽게 생성할 수 있는 스크립트가 있다. 

```bash
$ play new myFirstApp
```

실행하면 몇가지 정보를 물어온다.

- 어플리케이션 이름 (단지 표시를 위한것으로, 이 이름은 몇몇 메시지에서 사용될 것이다).
- 이 어플리케이션에서 사용될 템플릿. 디폴트로 스칼라 어플리케이션 이나 디폴트 자바 어플리케이션 둘중 하나를 선택할 수 있다.

[[images/playNew.png]]

> 이 시점에서 템플릿을 고른다는것이 후에 언어를 바꿀수 없다는 의미는 아니다. 예로 새로운 디폴트 자바 어플리케이션 템플릿을 이용하는 새로운 어플리케이션을 생성한후에 원하는 언제든 스칼라코드를 추가할 수 있다.

어플리케이션이 생성된 후 `play` 명령을 입력을 통해 [[Play console | PlayConsole]] 콘솔로 들어갈 수 있다.

```bash
$ cd myFirstApp
$ play
```

## Play를 설치하지 않고 새 어플리케이션 생성하기

Play 설치 없이도 sbt 를 이용해 새로운 어플리케이션을 생성할 수 있다.

> 필요하다면 우선 [sbt](http://www.scala-sbt.org/) 를 설치한다.

새로운 어플리케이션을 위한 새로운 디렉토리를 만들고 두가지가 추가된 sbt 빌드 스크립트를 설정한다. 

`project/plugins.sbt` 에 다음을 추가한다.

```scala
// The Typesafe repository 
resolvers += "Typesafe repository" at "http://repo.typesafe.com/typesafe/releases/"

// Use the Play sbt plugin for Play projects
addSbtPlugin("com.typesafe.play" % "sbt-plugin" % "%PLAY_VERSION%")
```

`%PLAY_VERSION%`를 이용하기 원하는 정확한 버전으로 변경해야한다. 만약 스냅샷 버전을 쓴다면 If you want to use a snapshot version, you will have to specify this additional resolver: 

```
// Typesafe snapshots
resolvers += "Typesafe Snapshots" at "http://repo.typesafe.com/typesafe/snapshots/"
```

In `build.sbt`:

```scala
import play.Project._

name := "My first application"

version := "1.0"

playScalaSettings
```

You can then launch the sbt console in this directory:

```bash
$ cd myFirstApp
$ sbt
```

sbt will load your project and fetch the dependencies.

> **Next:** [[Anatomy of a Play application | Anatomy]]
