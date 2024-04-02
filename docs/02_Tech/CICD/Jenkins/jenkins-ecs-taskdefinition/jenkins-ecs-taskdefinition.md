---
layout: default
title: 1-3. jenkins checkout
nav_order: 1
permalink: docs/02_Tech/CICD/Jenkins/jenkins-checkout-scm
parent: CICD
grand_parent: Tech
---

# jenkins pipeline에서 scm 사용하기

scm 사용하기

{: .no_toc }
![img.png](img.png)

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 글을 쓴 배경



## 글 요약


## 시작하기 전

Ubuntu version 22.04 LTS / 사용한 UBUNTU_AMI_ID =ami-09a7535106fbd42d5

사용한 docker image - jenkins/jenkins:jdk17 

젠킨슨 버전 - 2.449

사용한 레포지토리 주소 Jenkins-repo

---

## 1. jenkins checkout scm


### awscli를 활용한 EC2 Ubuntu OS 배포

#### piepline code snippet
```groovy
    checkout scmGit(
            userRemoteConfigs: [
                    [ url: 'https://git-codecommit.ap-northeast-2.amazonaws.com/v1/repos/portal-int-api-cloud']
            ],
            branches: [[name: '*/master']]
    )
```

### 코드 상세 설명

## 별첨

## FAQ
