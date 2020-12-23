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


# Namespace

**namespace: 커널의 resources을 분리하기 위해 사용되는 linux의 feature의 한 종류 이다. 하나의 프로세스가 하나의 리소스를 가리키고, 다른 프로세스는 다른 리소스를 가리키도록 한다. 또한, 컨테이너라 부르는 workspace를 독립시키기 위해서 docker에서 사용된다.**


### namespace 가 docekr 에서 어떻게 사용될까?
컨테이너를 run할때, docker가 컨테이너를 위한 namespaces들을 생성한다. 이 namespace 들은 독립을 위한 레이어를 제공한다.

#### Docker Engine이 linux에서 namespace를 사용하는 곳:
* pid: Process isolation
* net: Manage network interfaces
* ipc: Manage access to IPC resources (InterProcess Communication)
* mnt: Manage filesystem mount points
* uts: Isolate kernel and version identifiers (Unix Timesharing System)
