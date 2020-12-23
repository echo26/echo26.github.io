# Image

**Image: 다양한 레이어로 구성된 파일이다. 각각의 레이어는 Docker container안에 들어있는 코드를 실행 시킨다**
**Image: unchangeable, static file that includes executable code so it can run an isolated process.**


### Dockerfile?
**Dockerfile: 이미지를 만들기 위한 커맨드들을 모아놓은 text file이다. dockerfile을 통해 이미지 빌드를 자동화 한다. 또한, 커맨드 하나 하나가 레이어가 된다.**

### How to use Docker image?
* docker hub 에서 이미지를 가져옴.
* dockerd가 이미지를 다운 받아서 사용.



### Layer가 어떻게 Image가 되는지?
* 이미지들은 컨테이너화 될 때 합쳐져서 rootfs가 된다. (Union mount가 사용됨)
