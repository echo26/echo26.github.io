# drone

Continuous Integration(CI) platform

작동방식

* github hook을 통해 master 머지를 감지
* repository를 clone
* drone.yaml 에 있는 커맨드를 참고해서 build (drone cluster 에서 빌드 및 테스트)
