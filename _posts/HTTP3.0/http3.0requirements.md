---
title: "Requirements in applying HTTP 3.0"
date: 2020-11-02 17:00:00 -0400
categories: study update
___


# outline
1. Alt-svc 해더와 
2. 단계별 HTTP 3.0 적용
3. 현재 HTTP 3.0을 지원하는 browser & Server

## 1. Alt-svc 해더와 단계별 HTTP 3.0 적용
**Alt-svc**: 사용 가능한 대안의 서비스를 알려준다.

* eg)  Alt-Svc: h2="new.example.org:80"

`http2.0`을 사용해서 `new.example.org`의 `80`번 포트를 사용.

## 2. 단계별 HTTP 3.0 적용

동일 호스트에 2개의 포트를 운영. 하나는 2.0 하나는 3.0 지원
3.0에 보냈지만, 존재하지 않는 경우 alt-svc 응답을 통해 2.0으로 요청하도록 유도.

## 3. 현재 HTTP 3.0을 지원하는 browser & Server
* 비 연결형 프로토콜이다. 연결을 설정하고 해제하는 과정이 존재하지 않는다.
