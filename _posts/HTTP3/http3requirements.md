---
title: "Requirements in applying HTTP/3"
date: 2020-11-02 17:00:00 -0400
categories: study update
___


# outline
1. Alt-svc 해더와 
2. 단계별 HTTP/3 적용
3. 현재 HTTP/3을 지원하는 browser & Server

## 1. Alt-svc 해더와 단계별 HTTP/3 적용
**Alt-svc**: 사용 가능한 대안의 서비스를 알려준다.

* eg)  Alt-Svc: h3="new.example.org:80"

* 지속시간 : 기본 24시간. (ma=? 로 시간 설정 가능)

`http/2`을 사용해서 `new.example.org`의 `80`번 포트를 사용.

## 2. 단계별 HTTP/3 적용

#### example.com:20000에서 http/2 또는 http/1.1 수행 한다고 가정.
#### example.com:30000 에서 http/3을 수행.

1. Client가 example.com:20000으로 Request
2. examle.com:20000에서 Alt-svc와 함께 Response (Alt-svc: h3="example.com:30000" 또는, Alt-svc: h3":30000")
3. Client가 Alt-svc를 확인하고, HTTP/3을 지원한다면 호출처 변경
4. Client가 example.com:30000으로 Request (HTTP/3)
5. example.com:30000으로 부터 QUIC Response

![Image of Alt-svc](img/QUIC-AltSvc.png)


## 3. 현재 HTTP/3을 지원하는 browser & Server


| name | version | role | Implementation |
| ---- | ---- | ---- | --- |
| nginx | 1.19 (실험 버젼. production level은 아직) | server| [link](https://www.nginx.com/blog/introducing-technology-preview-nginx-support-for-quic-http-3/)|
| envoy | X | server| |
| haproxy | X | server| |
| apache | X | server| | 
| chrome | 지원하지 않지만, 실행 가능 | browser | [link](https://blog.chromium.org/2020/10/chrome-is-deploying-http3-and-ietf-quic.html)|
| safari | 14.0~14.2 지원하지 않지만, 실행 가능| browser | [link](https://www.iphoneincanada.ca/news/apple-safari-http3-ios-14/) |
| whale | X | browser | |
| IE | X | browser | |
| edge | 지원하지 않지만, 실행 가능 | browser | |


<br>

## HTTP/3 의 개선사항
congestion control 알고리즘에 따라 성능에 영향을 미칠 수 있습니다. Cloudflare의 테스트 결과입니다. 
BBRv1을 사용한 HTTP2와 CUBIC 을 사용한 HTTP/3입니다. [참조](https://blog.cloudflare.com/http-3-vs-http-2/)

![Image of comparison](img/performanceSmallData.png)

![Image of comparison](img/performanceHugeData.png)

