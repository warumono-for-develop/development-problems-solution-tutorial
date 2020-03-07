[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![Apache-2.0 License][license-shield]][license-url]
<!-- [![license](https://img.shields.io/github/license/:user/:repo.svg)](LICENSE) -->

<p align="center">
  <a href="https://github.com/warumono-for-develop/jenkins-installation-tutorial">
    <img src="https://github.com/warumono-for-develop/default/blob/master/logos/warumono-logo-492x500.png?raw=true" alt="Logo" width="292" height="300">
  </a>

  <h1 align="center">Jupyter Notebook Installation Tutorial</h1>

  <p align="center">
    Development Problems Solution Tutorial
    <br />
    <a href="https://github.com/warumono-for-develop/jenkins-installation-tutorial"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/warumono-for-develop/jenkins-installation-tutorial">View Tutorial</a>
    ·
    <a href="https://github.com/warumono-for-develop/jenkins-installation-tutorial/issues">Report Bug</a>
    ·
    <a href="https://github.com/warumono-for-develop/jenkins-installation-tutorial/issues">Request Feature</a>
  </p>
</p>



## Table of Contents 목차

- [Getting Started](#getting-started)
- [Solution](#solution)
    - [Case 1 <kbd>npm</kbd> + <kbd>gulp</kbd>](#case-1)
- [Usage](#usage)
- [FAQ](#faq)
- [Contact](#contact)
- [Acknowledgements](#acknowledgements)
- [License](#license)



## Getting Started
<!--
<details> 
  <summary>Collapse</summary>

Expanded

---
</details>
-->

### Requirements 요구사항

본 작업에 앞서 관련 대상 프로그램, 데이터 및 서버 등은 반드시 백업 완료 후 작업할 것을 권장   
본 작업을 작업하는 시점, 프로그램 버전 및 환경 등이 달라 설명 글의 진행 절차 또는 결과가 다소 다르거나 생략 또는 추가 작업이 있을 수 있음    
잘못된 용어 또는 정보가 다분히 포함되어 있는 비전문 지식을 바탕으로 설명되어 있으므로 공식 사이트 등에서 관련 정보를 미리 숙지하고 작업할 것을 권장

### About The Tutorial 지침서에 대하여

개발 진행 중 직면한 여러 형태의 많은 문제에 대해 경험을 토대로 해결한 작업 내용

### Prerequisites 전제조건

#### Required 필수사항

not yet

#### Optional 선택사항

not yet



## Solution

### Case 1

<kbd>npm</kbd> + <kbd>gulp</kbd>

#### Enviroments

- OS : macOS Catalina Version 10.15.3
- NodeJS : v13.1.0
- npm : 6.14.2

#### Problem

임의의 웹 프로젝트를 개발하기 위하여 환경 설정 중, npm 을 이용하여 gulp 를 로컬 프로젝트에 설치하는 과정에서 **gyp: No Xcode or CLT version detected!** 문제 발생

```sh
your-terminal> npm install -D gulp

> fsevents@1.2.11 install /Users/warumono/Development/GitHub/jenkiner/node_modules/fsevents
> node-gyp rebuild

No receipt for 'com.apple.pkg.CLTools_Executables' found at '/'.

No receipt for 'com.apple.pkg.DeveloperToolsCLILeo' found at '/'.

No receipt for 'com.apple.pkg.DeveloperToolsCLI' found at '/'.

gyp: No Xcode or CLT version detected!
gyp ERR! configure error 
gyp ERR! stack Error: `gyp` failed with exit code: 1
gyp ERR! stack     at ChildProcess.onCpExit (/usr/local/lib/node_modules/npm/node_modules/node-gyp/lib/configure.js:351:16)
gyp ERR! stack     at ChildProcess.emit (events.js:210:5)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:272:12)
gyp ERR! System Darwin 19.3.0
gyp ERR! command "/usr/local/Cellar/node/13.1.0/bin/node" "/usr/local/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /Users/warumono/Development/GitHub/jenkiner/node_modules/fsevents
gyp ERR! node -v v13.1.0
gyp ERR! node-gyp -v v5.1.0
gyp ERR! not ok 
npm WARN saveError ENOENT: no such file or directory, open '/Users/warumono/Development/GitHub/jenkiner/package.json'
npm WARN enoent ENOENT: no such file or directory, open '/Users/warumono/Development/GitHub/jenkiner/package.json'
npm WARN jenkiner No description
npm WARN jenkiner No repository field.
npm WARN jenkiner No README data
npm WARN jenkiner No license field.
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.11 (node_modules/fsevents):
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.11 install: `node-gyp rebuild`
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: Exit status 1

+ gulp@4.0.2
updated 1 package and audited 21406 packages in 3.413s

3 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

#### Reason

에러 로그 `gyp: No Xcode or CLT version detected!` 의 문제로 파악되어 찾아본 결과

대략적으로 Xcode 가 설치된 위치에 의해 충돌 (?) 또는 간섭 (?) 에 의한 문제로 판단

#### Solution

기존 설치되어 있는 Xcode 의 경로를 변경하는 방법으로 문제 해결

> sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer/

```sh
your-terminal> xcode-select --print-path
/Library/Developer/CommandLineTools
your-terminal> xcode-select --print-path
/Applications/Xcode.app/Contents/Developer
your-terminal> sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer/
your-terminal> xcode-select --print-path
/Applications/Xcode.app/Contents/Developer
```



## Contact

**email** warumono.for.develop@gmail.com    
**blog** https://warumono-for-develop.github.io

## Acknowledgements

not yet

## License

Distributed under the MIT License. See [`LICENSE`][license-url] for more information.

<!-- MARKDOWN LINKS & IMAGES -->

<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[spring-boot-restful-api-server-template]: https://github.com/warumono-for-develop/spring-boot-restful-api-server-template "Spring Boot RESTFul API Server Template"
[jenkins-installation-tutorial]: https://github.com/warumono-for-develop/jenkins-installation-tutorial "Docker Installation Tutorial"
[jenkins-installation-tutorial]: https://github.com/warumono-for-develop/jenkins-installation-tutorial "Jenkins Installation Tutorial"
[jenkins-installation-tutorial]: https://github.com/warumono-for-develop/jenkins-installation-tutorial "Jupyter Notebook Installation Tutorial"

[contributors-shield]: https://img.shields.io/github/contributors/warumono-for-develop/jenkins-installation-tutorial.svg?style=flat-square
[contributors-url]: https://github.com/warumono-for-develop/jenkins-installation-tutorial/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/warumono-for-develop/jenkins-installation-tutorial.svg?style=flat-square
[forks-url]: https://github.com/warumono-for-develop/jenkins-installation-tutorial/network/members
[stars-shield]: https://img.shields.io/github/stars/warumono-for-develop/jenkins-installation-tutorial.svg?style=flat-square
[stars-url]: https://github.com/warumono-for-develop/jenkins-installation-tutorial/stargazers
[issues-shield]: https://img.shields.io/github/issues/warumono-for-develop/jenkins-installation-tutorial.svg?style=flat-square
[issues-url]: https://github.com/warumono-for-develop/jenkins-installation-tutorial/issues
[license-shield]: https://img.shields.io/github/license/warumono-for-develop/jenkins-installation-tutorial.svg?style=flat-square
[license-url]: https://github.com/warumono-for-develop/jenkins-installation-tutorial/blob/master/LICENSE
[product-screenshot]: images/screenshot.png

