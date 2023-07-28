<img align="right" src="spring-batch-docs/src/main/asciidoc/images/spring-batch.png" width="200" height="200">

# Spring Batch [![build status](https://github.com/spring-projects/spring-batch/actions/workflows/continuous-integration.yml/badge.svg)](https://github.com/spring-projects/spring-batch/actions/workflows/continuous-integration.yml)

Spring Batch는 경량이면서 포괄적인 배치 프레임워크로, 기업 시스템의 일상적인 운영에 필수적인 견고한 배치 응용 프로그램 개발을 가능하게 하는 것을 목표로 합니다. Spring Batch는 [Spring Framework](https://github.com/spring-projects/spring-framework)에서 이미 알려진 생산성, POJO 기반 개발 접근 방식 및 전반적인 사용 편의성 능력을 바탕으로하며, 필요할 때 개발자가 더 고급 기업 서비스에 접근하고 활용하기 쉽도록 합니다.

만약 Batch 응용 프로그램을 위한 런타임 오케스트레이션 도구를 찾거나 현재와 과거의 실행 내역을 볼 수 있는 관리 콘솔이 필요하다면, [Spring Cloud Data Flow](https://cloud.spring.io/spring-cloud-dataflow/)를 살펴보세요. 이는 Spring Batch 응용 프로그램을 포함한 데이터 통합 기반 마이크로서비스를 배포하고 실행하기 위한 오케스트레이션 도구입니다.

# Getting Started

## Guide

이는 Spring Boot 기반의 새로운 Spring Batch 프로젝트를 시작하는 가장 빠른 방법입니다. Getting Started Guide에서 자세한 내용을 확인할 수 있습니다.: [Creating a Batch Service](https://spring.io/guides/gs/batch-processing/).

## Samples

여러 가지 샘플을 시도해볼 수 있는 내용들은 다음 링크에서 찾을 수 있습니다:: [Spring Batch Samples](https://github.com/spring-projects/spring-batch/tree/main/spring-batch-samples).

# Getting Help (도움 얻기)

만약 질문이나 지원 요청이 있다면, [GitHub Discussions](https://github.com/spring-projects/spring-batch/discussions)에서 새로운 토론을 열어주시거나 [StackOverflow](https://stackoverflow.com/questions/tagged/spring-batch)에서 질문을 하시면 됩니다. 더 많은 도움을 받을 수 있을 것입니다.

질문이나 지원 요청을 위해 [Issue Tracker](https://github.com/spring-projects/spring-batch/issues)에 이슈를 생성하지 마십시오.
이슈 트래커는 오로지 버그 보고 및 기능 요청을 위해 전용으로 유지하고자 합니다.

# Reporting issues

Spring Batch는 버그와 기능 요청을 기록하기 위해 [GitHub Issues](https://github.com/spring-projects/spring-batch/issues)를 사용합니다. 이슈를 등록하고자 하는 경우, 아래의 권장 사항을 따라주시기 바랍니다:

* 이슈를 등록하기 전에, 이미 해당 문제를 누군가가 보고했는지 여부를 확인하기 위해 이슈 트래커를 검색해주세요. 해당 문제가 이미 존재하지 않는다면, 새로운 이슈를 생성해주세요.
* 이슈 보고서에 가능한 많은 정보를 제공해 주시기 바랍니다. 이를 위해 [Issue Reporting Template](https://github.com/spring-projects/spring-batch/blob/main/.github/ISSUE_TEMPLATE/bug_report.md)를 따라주시기 바랍니다.
* 코드를 붙여넣거나 스택 트레이스를 포함해야 할 경우, 텍스트 앞뒤에 Markdown 이스케이프 (```)를 사용해주세요.

중요하지 않은 버그에 대해서는, 문제를 복제하는 테스트 케이스 또는 프로젝트를 만들어서 이슈에 첨부해주세요. 자세한 내용은 [Issue Reporting Guidelines](https://github.com/spring-projects/spring-batch/blob/main/ISSUE_REPORTING.md)를 참고해주세요.

# Reporting Security Vulnerabilities (보안 취약점 보고서 제출하기)

저희 보안 정책 [Security policy](https://github.com/spring-projects/spring-batch/security/policy).

# Building from Source (소스 코드로부터 빌드하기)

## Using the Command Line (커맨드 라인)

GitHub 홈페이지에서 URL을 사용하여 Git 저장소를 클론하기:

    $ git clone git@github.com:spring-projects/spring-batch.git
    $ cd spring-batch

Maven은 Spring Batch에서 사용되는 빌드 도구입니다. 다음 명령어를 사용하여 프로젝트를 빌드할 수 있습니다.:

    $ ./mvnw package

만약 모든 통합 테스트를 포함한 완전한 빌드를 수행하려면, 다음 명령어를 실행하세요:

    $ ./mvnw verify


알려드립니다. 일부 통합 테스트는 Docker를 기반으로 하므로, 완전한 빌드를 실행하기 전에 Docker가 실행 중이고 정상적으로 작동하는지 확인해야 합니다.

참고 문서(Reference Documentation)를 생성하려면 다음 명령어를 실행하세요:

```
$ ./mvnw javadoc:aggregate
$ cd spring-batch-docs
$ ../mvnw site
```

참고 문서(Reference Documentation)는 spring-batch-docs/target 디렉토리에서 찾을 수 있습니다.

## Using Docker

Docker 컨테이너 내에서 프로젝트를 빌드하려면 다음과 같이 진행할 수 있습니다:

```
$> docker run -it --mount type=bind,source="$(pwd)",target=/spring-batch maven:3-openjdk-17 bash
#> cd spring-batch
#> ./mvnw package
```

Docker 컨테이너 내에서 호스트에서 클론한 소스 코드를 마운트하는 대신, 컨테이너 내에서 소스 코드의 복사본을 사용하여 작업하고자 한다면 다음과 같이 진행할 수 있습니다:

```
$> docker run -it maven:3-openjdk-17 bash
#> git clone https://github.com/spring-projects/spring-batch.git
#> cd spring-batch
#> ./mvnw package
```

# Contributing to Spring Batch

We welcome contributions in any kind! Here are some ways for you to contribute to the project:

* Get involved with the Spring Batch community on [Twitter](https://twitter.com/springbatch), [GitHub Discussions](https://github.com/spring-projects/spring-batch/discussions) and [StackOverflow](https://stackoverflow.com/questions/tagged/spring-batch) by responding to questions and joining the debate.
* Create [issues](https://github.com/spring-projects/spring-batch/issues) for bugs and new features or comment and vote on the ones that you are interested in.
* Help us reproduce issues marked with [status: need-help-to-reproduce](https://github.com/spring-projects/spring-batch/labels/status%3A%20need-help-to-reproduce) by following the [Issue Reporting Guidelines](https://github.com/spring-projects/spring-batch/blob/main/ISSUE_REPORTING.md).
* Github is for social coding: if you want to write code, we encourage contributions through pull requests. If you want to contribute code this way, please familiarize yourself with the process outlined here: [Contributor Guidelines](https://github.com/spring-projects/spring-batch/blob/main/CONTRIBUTING.md).
* Watch for Spring Batch related articles on [spring.io](https://spring.io).

Before we accept pull requests, we will need you to sign the [contributor's agreement](https://support.springsource.com/spring_committer_signup).  Signing the contributor's agreement does not grant anyone commit rights to the main repository, but it does mean that we can accept your contributions, and you will get an author credit if we do.  Active contributors might be asked to join the core team, and given the ability to merge pull requests.

# Code of Conduct (행동 규칙)

Please see our [code of conduct](https://github.com/spring-projects/.github/blob/main/CODE_OF_CONDUCT.md).

# License

Spring Batch is Open Source software released under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0.html).
