# SWE_2021_41_2024_2_week_6
---
## Week 4 Assignment
- https://github.com/CVEZeroday/SWE_2021_41_2024_2_week_4
```python
def isHappy(n):

  curr = n
  visited = [n]
  while True:
    tmp = 0

    while curr > 0:
      tmp += (curr % 10) ** 2
      curr = curr // 10

    if tmp == 1:
      return True

    if tmp not in visited:
      visited.append(tmp)
    else:
      return False

    curr = tmp
```
- isHappy 함수는 n을 입력받아 n이 happy number인지 판별하는 함수입니다.
- `visited`는 계산 과정에서 등장했던 수들의 리스트입니다.
- `while curr > 0:`부분의 루프는 규칙에 따라 다음 숫자를 구하는 루프입니다.
- 만약 구한 숫자가 1이면, `curr`는 1에서 무한 반복할 것이기 때문에 `True`를 리턴합니다.
- 만약 구한 숫자가 이미 나왔던 숫자라면, 무한 반복되는 사이클이 만들어진 것이므로 `False`를 리턴합니다.
- 만약 두 경우가 모두 아니라면, `visited`에 `curr`을 넣은 뒤 계속 반복합니다.
---
## Week 5 Assignment
> ```bash
> docker exec ossp_container cat /etc/os-release
> ```
> ```bash
> # 실행 결과
> PRETTY_NAME="Ubuntu 24.04.1 LTS"
> NAME="Ubuntu"
> VERSION_ID="24.04"
> VERSION="24.04.1 LTS (Noble Numbat)"
> VERSION_CODENAME=noble
> ID=ubuntu
> ID_LIKE=debian
> HOME_URL="https://www.ubuntu.com/"
> SUPPORT_URL="https://help.ubuntu.com/"
> BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
> PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
> UBUNTU_CODENAME=noble
> LOGO=ubuntu-logo
> ```
> - `docker exec <container_name> <command>` 명령어는 컨테이너 외부에서 컨테이너에 쉘 명령어를 입력할 수 있도록 해주는 명령어입니다.
> - `cat /etc/os-release`는 해당 컨테이너의 OS 버전을 출력합니다.

> ```bash
> docker exec ossp_container git --version
> ```
> ```bash
> # 실행 결과
> git version 2.43.0
> ```
> - `git --version`은 설치되어 있는 git의 버전을 출력합니다.

> ```bash
> docker exec ossp_container python3 --version
> ```
> ```bash
> #실행 결과
> Python 3.12.3
> ```
> - `python3 --version`은 설치되어 있는 python3의 버전을 출력합니다.

> ```bash
> docker inspect --format="{{ .HostConfig.Binds }}" ossp_container
> ```
> ```bash
> # 실행 결과
> [/home/cvezeroday/programming/ossp:/mnt/ossp_container_dir]
> ```
> - `docker inspect --format="{{ .HostConfig.Binds }}" <container_name>` 명령어는 mount된 디렉토리를 출력하는 명령어입니다.
