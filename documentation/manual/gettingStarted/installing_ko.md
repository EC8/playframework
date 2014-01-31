<!--- Copyright (C) 2009-2013 Typesafe Inc. <http://www.typesafe.com> -->
# Play 설치하기

## 설치 전 필요조건

Play framework를 실행하려면 JDK 6 이상이 필요하다(http://www.oracle.com/technetwork/java/javase/downloads/index.html).

> MacOS를 사용한다면 Java는 내장돼 있다. Linux를 쓴다면 Sun JDK나 OpenJDK 중의 하나를 사용할 수 있다(많은 리눅스 배포판에서 gcj 하지 않으면 기본 명령어는 Java이다). Windows를 사용하면 최신 버전의 JDK 패키지를 다운로드 받아 설치하면 된다.

> 주의, MacOS의 Java 7(pre update 9)은 대용량 파일 업로드가 중지하는 등 futures 와 iteratees 에 문제를 일으키는 버그가 있다. MacOS에서 Java 7을 사용하려면 최신 버전을 사용해야 한다.

현재 경로에서 'java'와 'javac'가 실행되면 된다. (shell 프롬프트에서 `java -version`과 `javac -version`을 입력해서 확인할 수 있다.)

## 바이너리 패키지 다운로드

### Typesafe Activator 사용하기

Play를 [Typesafe Activator](http://typesafe.com/activator)를 사용해서 설치할 수 있다. 현재 페이지는 Play standalone 배포판에 대한 설치 문서이고 Typesafe Activator를 사용하려면 [링크](http://typesafe.com/platform/getstarted)를 따라가 Play를 설치해볼 수 있다.

### Play standalone 사용하기

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
