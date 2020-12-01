---
title: "HTTP 2.0"
date: 2020-11-02 17:00:00 -0400
categories: study update
___

# HTTP 3.0

## Outline
1. [TCP 의 특징](tcpDegradation.md)
* TCP에 대한 기본 설명
* 성능 저하 요인
- 3 way handshaking
- TCP HOL Blocking

2. [HTTP 3.0의 특징](http3.0details.md)
- UDP의 정의 및 특징
- O-RTT
- Multiplexing
- HPACK & QPACK
- HTTP 1.1 vs 2.0 vs 3.0

3. [HTTP 3.0 적용시 고려 사항](http3.0requirements.md)



## Basics
공통점은 비슷하다.
* 스트림 제공
* 서버 푸시 지원
* 헤더 압축을 제공한다. QPACK과 HPACK은 설계상 비슷하다.
* 스트림을 이용해서 하나의 연결을 통해 멀티플렉싱을 제공한다.
* 스트림에 우선순위를 정한다.
**이 부분은 HTTP/1.1과의 차이라고 봐도 될 듯**


* QUIC의 0-RTT 핸드쉐이크 덕에 HTTP/3에서는 이른 데이터 지원이 더 낫게 잘 동작한다. TCP Fast Open과 TLS는 더 적은 데이터를 보내지만, 종종 문제점에 직면한다.
* HTTP/3는 QUIC 덕에 TCP + TLS보다 훨씬 더 빠른 핸드쉐이크를 제공한다.
* HTTP/3에는 안전하지 않거나 암호화되지 않은 버전이 없다. 인터넷에서 드물기는 하지만 HTTP/2는 HTTPS 없이 구현하고 사용할 수 있다.
* HTTP/2가 ALPN 확장을 이용하여 즉시 TLS 핸드쉐이크 협상을 완료할 수 있는 반면 HTTP/3는 QUIC을 사용하므로 클라이언트에 이 사실을 알리기 위해 Alt-Svc: 헤더 응답이 먼저 있어야 한다.
