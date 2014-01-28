<!--- Copyright (C) 2009-2013 Typesafe Inc. <http://www.typesafe.com> -->
# Play 설치하기

## 설치 전 필요조건

Play framework를 실행하려면 JDK 6 이상이 필요하다(http://www.oracle.com/technetwork/java/javase/downloads/index.html).

> MacOS를 사용한다면 Java는 내장돼 있다. Linux를 쓴다면 Sun JDK나 OpenJDK 중의 하나를 사용할 수 있다(많은 리눅스 배포판에서 gcj 하지 않으면 기본 명령어는 Java이다). Windows를 사용하면 최신 버전의 JDK 패키지를 다운로드 받아 설치하면 된다.

> 주의, MacOS의 Java 7(pre update 9)은 대용량 파일 업로드가 중지하는 등 futures 와 iteratees 에 문제를 일으키는 버그가 있다. MacOS에서 Java 7을 사용하려면 최신 버전을 사용해야 한다.

Be sure to have the `java` and `javac` commands in the current path (you can check this by typing `java -version` and `javac -version` at the shell prompt). 

## Download the binary package

### Using Typesafe Activator

Play can be installed using [Typesafe Activator](http://typesafe.com/activator).  The documentation on this page is about installing the Play standalone distribution.  If you would like to use Typesafe Activator, then follow the instructions [here](http://typesafe.com/platform/getstarted) to install Play.

### Using Play standalone

Download the latest [Play standalone distribution](http://www.playframework.com/download) and extract the archive to a location where you have both read **and write** access. (Running `play` writes some files to directories within the archive, so don't install to `/opt`, `/usr/local` or anywhere else you’d need special permission to write to.)

## Add the play script to your PATH

For convenience, you should add the framework installation directory to your system PATH. On UNIX systems, this means doing something like:

```bash
export PATH=$PATH:/relativePath/to/play
```

On Windows you’ll need to set it in the global environment variables. This means update the PATH in the environment variables and don't use a path with spaces.

> If you’re on UNIX, make sure that the `play` script is executable (otherwise do a `chmod a+x play`).

> If you're behind a proxy make sure to define it with `set HTTP_PROXY=http://<host>:<port>` on Windows or `export  HTTP_PROXY=http://<host>:<port>` on UNIX.

## Check that the play command is available

From a shell, launch the `play help` command. 

```bash
$ play help
```

If everything is properly installed, you should see the basic help:

[[images/play.png]]

> **Next:** [[Creating a new application | NewApplication]]
