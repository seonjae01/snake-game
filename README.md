# Snake Game

이 프로젝트는 C++와 ncurses 라이브러리를 사용하여 만든 Snake Game입니다.

## 🕹️ 게임 규칙

- **방향키** (위, 아래, 왼쪽, 오른쪽)로 뱀을 조작합니다.
- **아이템**:
  - **🟩** Growth Item: 먹으면 뱀의 길이가 1 늘어납니다.
  - **🟥** Poison Item: 먹으면 뱀의 길이가 1 줄어듭니다.
- **미션**: 각 맵에서 주어진 미션을 클리어하면, **다음 맵으로 이동**하며, **미션의 난이도가 상승**합니다.
  - **미션 1**: **🟩** Growth Item X개 먹기
  - **미션 2**: **🟥** Poison Item Y개 먹기
  - **미션 3**: **🟪** Gate 이용하기
  - **미션 4**: **🟦** 뱀을 일정 길이 이상 도달시키기
- **게임 오버**: **⬜ 벽** 또는 자기 몸에 부딪히면 게임이 종료됩니다. **🟦 뱀의 길이가 3 미만**이면 게임이 종료됩니다.
- **🟪 Gate**: 주기적으로 나타나는 **Gate**를 통해 반대 **Gate**로 이동할 수 있습니다.
- **⬜ Wall**: 벽에 부딪히면 게임 오버가 됩니다. **Gate**는 **Wall**에서 생성됩니다.
- **🟦 Snake**: 뱀의 몸체입니다. **Item**을 먹어 길이를 늘릴 수 있습니다.

## 💻 실행 방법

### 1. 필수 라이브러리 설치

이 프로젝트는 **ncurses** 라이브러리를 사용합니다.

- **Ubuntu/Debian**:
  ```bash
  sudo apt-get install libncurses5-dev libncursesw5-dev
  ```
### 2. 프로젝트 클론

Git을 사용하여 프로젝트를 클론합니다:

```bash
git clone https://github.com/seonjae01/snake-game.git
cd snake-game
```
### 3. 빌드

프로젝트의 루트 디렉토리에서 빌드를 위해 다음 절차를 따릅니다.

- 빌드 디렉토리 생성

```bash
mkdir build
cd build
```
- Make 실행

```
cmake ..
```

- Make로 빌드

```
make
```

### 4. 게임 실행

```
./snakegame
```

## 📋 프로젝트 구조

```bash
.
├── CMakeLists.txt         # CMake 빌드 설정 파일
├── LICENSE                # 프로젝트 라이선스 파일
├── README.md              # 프로젝트 설명 파일
├── src/                   # 소스 코드 디렉토리
    ├── main.cpp           # 게임의 메인 소스 파일
    ├── game.cpp           # 게임 로직
    ├── game.hpp
    ├── gate.cpp           # 게이트 관련 로직
    ├── gate.hpp
    ├── item.cpp           # 아이템 관련 로직
    ├── item.hpp
    ├── mission.cpp        # 미션 관련 로직
    ├── mission.hpp
    ├── point.cpp          # 좌표 관련 로직
    ├── point.hpp
    ├── score.cpp          # 점수 관련 로직
    ├── score.hpp
    ├── screen.cpp         # 화면 출력 관련 로직
    ├── screen.hpp
    ├── snake.cpp          # 뱀 관련 로직
    ├── snake.hpp
    ├── stage.cpp          # 맵 관련 로직
    ├── stage.hpp
    ├── snakeGame.cpp      # 게임 상태 및 관리
    └── snakeGame.hpp
```

## 🛠️ 빌드 에러 해결

1. **`ncurses` 라이브러리 설치**:
    - `ncurses`는 터미널 기반 사용자 인터페이스를 개발할 때 필요한 라이브러리입니다. 해당 라이브러리가 없다면 프로젝트가 빌드되지 않으므로, 필요한 경우 설치해야 합니다.
    - 이 부분은 **Ubuntu/Debian** 시스템에서 설치하는 방법을 설명하며, 다른 플랫폼에 대한 설치 방법은 해당 시스템에 맞게 설치하면 됩니다.

2. **CMake 버전 확인**:
    - 프로젝트를 빌드하려면 **CMake 3.22 이상의 버전**이 필요하므로, 현재 설치된 버전이 요구 사항에 맞는지 확인하고, 필요하면 CMake를 업데이트해야 합니다.
