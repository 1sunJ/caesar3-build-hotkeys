# 시저3 Julius 건설 단축키 패치

[English](README.md) | **한국어**

시저3(Caesar III)의 오픈소스 엔진 [Julius](https://github.com/bvschaik/julius) **1.8.0**에 키보드 건설 단축키를 추가한 수정판입니다.
사이드바 버튼을 클릭하지 않고 키보드만으로 모든 건물을 고를 수 있습니다.

```
A → 3        분수
G → 1 → 4    마르스 작은 신전
H            주거지
```

## 기능

1. **카테고리 키**: 키 하나로 사이드바 건설 메뉴(물, 보건, 종교 …)가 열립니다.
2. **숫자로 항목 선택**: 건설 메뉴가 열려 있을 때 `1`~`9`를 누르면 그 순서의 건물이 선택됩니다. 신전·농장처럼 하위 메뉴가 있으면 숫자를 이어서 누르면 됩니다.
3. **메뉴 번호 표시**: 건설 메뉴 각 항목 왼쪽에 번호가 표시됩니다.
4. **버튼 단축키 표시**: 사이드바 건설 버튼 오른쪽 아래에 해당 키가 표시됩니다.

게임 규칙은 전혀 바꾸지 않으므로 **세이브 파일은 원본 Julius 1.8.0, 원본 시저3와 그대로 호환됩니다.**

## 기본 단축키

| 카테고리 | 키 | 카테고리 | 키 |
|---|---|---|---|
| 주거 | `H` | 교육 | `S` |
| 철거 | `X` | 오락 | `N` |
| 도로 | `R` | 행정 | `V` |
| 물 | `A` | 기술 | `E` |
| 보건 | `K` | 군사 | `M` |
| 종교 | `G` | 산업 | `I` |

- 주거, 철거, 도로는 하위 메뉴가 없어서 키를 누르면 바로 건설 도구가 선택됩니다.
- 기존 키(오버레이 `W` `F` `D` `C` `T`, 일시정지 `P`, 군단 `L`, 복제 등)와 겹치지 않게 배치했습니다.
- 모든 키는 게임 안에서 바꿀 수 있습니다. ([설정](#설정) 참고)

### 메뉴 안에서

| 키 | 동작 |
|---|---|
| `1`~`9` (숫자패드 포함) | 메뉴의 n번째 항목 선택 |
| 같은 카테고리 키 | 메뉴 닫기 |
| 다른 카테고리 키 | 그 메뉴로 바로 전환 |
| `H` `X` `R` | 메뉴를 닫고 주거·철거·도로 선택 |
| `Esc` / 오른쪽 클릭 | 메뉴 닫기 |

메뉴가 닫혀 있을 때 숫자키는 지금처럼 조언자 화면을 엽니다.

### 메뉴 항목 순서

아래는 모든 건물이 허용된 경우의 순서입니다. **현재 임무에서 지을 수 없는 건물은 메뉴에 나오지 않고, 번호는 보이는 항목 기준으로 매겨집니다.** 그러니 화면에 표시된 번호를 보고 누르세요.

| 메뉴 (키) | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---|---|---|---|---|---|---|---|---|---|
| 물 (`A`) | 저수지 | 수로 | 분수 | 우물 | | | | | |
| 보건 (`K`) | 이발소 | 목욕탕 | 진료소 | 병원 | | | | | |
| 종교 (`G`) | 작은 신전 ▶ | 큰 신전 ▶ | 신탁소 | | | | | | |
| 교육 (`S`) | 학교 | 학술원 | 도서관 | 선교소 | | | | | |
| 오락 (`N`) | 극장 | 원형극장 | 콜로세움 | 전차 경기장 | 검투사 학교 | 사자 우리 | 배우 양성소 | 전차 제작소 | |
| 행정 (`V`) | 포룸 | 원로원 | 총독 관저 | 총독 저택 | 총독 궁전 | 작은 동상 | 중간 동상 | 큰 동상 | 개선문 |
| 기술 (`E`) | 정원 | 광장 | 기술자 초소 | 낮은 다리 | 배 다리 | 조선소 | 부두 | 어선 선착장 | |
| 군사 (`M`) | 성벽 | 탑 | 성문 | 감독관 초소 | 요새 ▶ | 군사 학교 | 병영 | | |
| 산업 (`I`) | 농장 ▶ | 원자재 ▶ | 작업장 ▶ | 시장 | 곡물 창고 | 창고 | | | |

▶ 표시는 하위 메뉴입니다. 예를 들어 작은 신전(`G` → `1`) 안은 케레스, 넵투누스, 메르쿠리우스, 마르스, 베누스 순서입니다.
게임 안 건물 이름은 사용하는 한글 패치에 따라 조금 다를 수 있습니다.

## 설치

**준비물**: 시저3 원본 게임 파일(Steam/GOG 등). Julius를 이미 쓰고 있다면 그 폴더를 그대로 쓰면 됩니다.

1. 게임을 종료합니다.
2. 게임 폴더를 엽니다. Steam판이라면 보통 아래 경로입니다.
   ```
   C:\Program Files (x86)\Steam\steamapps\common\Caesar 3\C3
   ```
3. 폴더에 `julius.exe`, `SDL2.dll`, `SDL2_mixer.dll`이 이미 있다면 **다른 이름으로 백업**해 둡니다. (예: `julius.exe.bak`)
4. 이 패키지의 아래 3개 파일을 게임 폴더에 복사합니다.
   - `julius.exe`
   - `SDL2.dll`
   - `SDL2_mixer.dll`
5. `julius.exe`를 실행합니다.

### Steam 플레이 버튼으로 실행하고 싶다면

Steam의 플레이 버튼은 게임 폴더의 `c3.exe`를 실행합니다. 플레이 버튼으로 이 수정판을 켜려면:

1. 기존 `c3.exe`를 `c3.exe.bak`으로 이름을 바꿔 백업합니다.
2. 이 패키지의 `julius.exe`를 복사해서 이름을 `c3.exe`로 바꿉니다.

Steam의 "게임 파일 무결성 검사"를 실행하면 `c3.exe`가 원래 파일로 돌아갈 수 있습니다. 그때는 다시 바꿔 주면 됩니다.

### 한글

한글로 플레이하려면 Julius용 한글 패치(`korean-v2.555`와 한국어 언어 파일)가 게임 폴더에 있어야 합니다. 이 수정판은 한글 패치를 그대로 사용하며, 추가된 설정 문구도 한국어로 번역되어 있습니다.

## 제거

1. 복사한 `julius.exe`, `SDL2.dll`, `SDL2_mixer.dll`을 지웁니다.
2. 백업해 둔 파일의 이름을 원래대로 되돌립니다.

설정 파일에 추가된 항목은 원본 Julius가 무시하므로 그대로 둬도 됩니다.

## 설정

메인 메뉴 또는 게임 중 메뉴에서 Julius 설정 화면을 엽니다.

- **단축키 표시 켜기/끄기**: 설정 화면의 "건설 버튼과 메뉴에 단축키 표시"를 체크하거나 해제합니다. 끄면 사이드바 글자와 메뉴 번호만 사라지고 단축키는 계속 동작합니다.
  (`julius.ini`의 `ui_show_build_hotkeys=1` / `0`)
- **키 바꾸기**: 설정 화면 아래쪽의 단축키 설정(Configure hotkeys)에서 "건설 단축키" 항목을 찾아 바꿉니다. 바꾼 키는 사이드바 버튼 표시에도 바로 반영됩니다.
- **키 지우기**: 단축키 설정에서 지운 키는 저장 후에도 지운 상태로 유지됩니다.

### 이미 단축키를 바꿔 쓰고 있었다면

`julius-hotkeys.ini`가 이미 있는 경우에도 새 카테고리 키가 자동으로 추가됩니다. 다만 **이미 다른 기능에 쓰고 있는 키는 덮어쓰지 않고 비워 둡니다.** 그런 항목은 단축키 설정 화면에서 직접 지정하세요.

## 문제 해결

| 증상 | 확인할 것 |
|---|---|
| 실행하면 "원본 파일이 필요하다"는 메시지가 뜸 | `julius.exe`를 시저3 데이터 파일(`c3.eng`, `C3.sg2` 등)이 있는 폴더에 넣었는지 확인 |
| 실행 직후 DLL 오류 | `SDL2.dll`, `SDL2_mixer.dll`도 같이 복사했는지 확인 |
| 키를 눌러도 메뉴가 안 열림 | 그 카테고리에 현재 임무에서 지을 수 있는 건물이 없으면 사이드바 버튼처럼 열리지 않음. 다른 건물을 짓는 중(드래그 중)에는 열리지 않음 |
| 한글이 깨짐 | Julius용 한글 패치 파일이 게임 폴더에 있는지, 설정 화면의 언어가 한국어인지 확인 |

## 직접 빌드하기

배포된 `julius.exe` 대신 직접 빌드하고 싶은 분을 위한 방법입니다. (Windows, 32비트)

**필요한 것**: Git, Visual Studio 2022 (C++ 데스크톱 개발 워크로드), CMake 3.15 이상

패치가 이미 적용된 소스는 [1sunJ/julius](https://github.com/1sunJ/julius)의 `build-hotkeys` 브랜치에도 있습니다. 1단계 대신 `git clone -b build-hotkeys https://github.com/1sunJ/julius.git julius`를 실행해도 됩니다.

이 `julius` 폴더에서 아래 명령을 실행합니다.

```bash
# 1. Julius 1.8.0 소스를 받고 패치 적용
git clone https://github.com/bvschaik/julius.git
cd julius
git checkout v1.8.0
git apply ../patch/julius-1.8.0-build-hotkeys.patch

# 2. SDL2 개발 파일을 ext/SDL2 아래에 압축 해제
#    https://github.com/libsdl-org/SDL/releases/tag/release-2.32.8        → SDL2-devel-2.32.8-VC.zip
#    https://github.com/libsdl-org/SDL_mixer/releases/tag/release-2.8.1   → SDL2_mixer-devel-2.8.1-VC.zip
#    결과: ext/SDL2/SDL2-2.32.8/, ext/SDL2/SDL2_mixer-2.8.1/

# 3. 빌드 (C 런타임을 정적으로 포함해서 VC++ 재배포 패키지 없이 실행되게 함)
cd ..
cmake -S julius -B build -G "Visual Studio 17 2022" -A Win32 \
  -DCMAKE_POLICY_VERSION_MINIMUM=3.5 \
  -DCMAKE_POLICY_DEFAULT_CMP0091=NEW \
  -DCMAKE_MSVC_RUNTIME_LIBRARY=MultiThreaded
cmake --build build --config Release
```

결과물은 `build/Release/julius.exe`입니다. 실행하려면 SDL2 패키지의 `lib/x86/SDL2.dll`, `lib/x86/SDL2_mixer.dll`을 같은 폴더에 두세요.

- `CMAKE_POLICY_VERSION_MINIMUM=3.5`는 CMake 4.x에서만 필요합니다. 그보다 낮은 버전에서는 빼도 됩니다.
- MinGW나 Linux/macOS에서도 Julius의 [빌드 문서](https://github.com/bvschaik/julius/blob/master/doc/BUILDING.md)대로 빌드할 수 있습니다. 패치는 플랫폼에 상관없이 적용됩니다.

### 바뀐 소스 파일

| 파일 | 내용 |
|---|---|
| `src/core/hotkey_config.c/.h` | 카테고리 단축키 9개 추가, 기본 키 지정, 기존 단축키 파일에 새 기본값 보충 |
| `src/input/hotkey.c/.h` | 카테고리 키 처리, 건설 메뉴가 열려 있을 때 숫자키를 항목 선택으로 처리 |
| `src/window/build_menu.c` | 단축키로 항목 선택·메뉴 전환, 항목 번호 표시 |
| `src/window/city.c/.h` | 카테고리 키로 건설 메뉴 열기 |
| `src/widget/sidebar/city.c` | 사이드바 건설 버튼에 단축키 표시 |
| `src/core/config.c/.h`, `src/window/config.c` | "단축키 표시" 설정 추가 |
| `src/window/hotkey_config.c` | 단축키 설정 화면에 카테고리 항목 추가 |
| `src/translation/*` | 설정 문구 (영어, 한국어) |

## 패키지 구성

```
julius-build-hotkeys-1.8.0/
├── julius.exe                           수정판 실행 파일 (32비트)
├── SDL2.dll                             SDL 2.32.8
├── SDL2_mixer.dll                       SDL_mixer 2.8.1
├── julius-1.8.0-build-hotkeys.patch     소스 변경 사항 (Julius v1.8.0 기준)
├── README.md                            영어 설명서
├── README.ko.md                         이 문서 (한국어)
└── licenses/
    ├── Julius-LICENSE.txt               GNU AGPL v3
    ├── SDL2-LICENSE.txt                 zlib License
    └── SDL2_mixer-LICENSE.txt           zlib License
```

## 라이선스

- Julius는 **GNU AGPL v3** 라이선스입니다. 이 수정판도 같은 라이선스를 따릅니다. 수정판의 전체 소스는 [Julius v1.8.0](https://github.com/bvschaik/julius/tree/v1.8.0)에 동봉된 `julius-1.8.0-build-hotkeys.patch`를 적용한 것과 같습니다. 이 프로그램을 다시 배포할 때는 패치 파일(또는 수정한 소스)을 함께 제공해 주세요.
- SDL2, SDL2_mixer는 zlib 라이선스입니다.
- 시저3 게임 데이터(그래픽, 소리, 맵 등)는 포함되어 있지 않으며 원저작권자에게 권리가 있습니다. 게임을 정식으로 구입해서 사용하세요.

이 수정판은 Julius 공식 배포판이 아닙니다. 이 수정판과 관련된 문제는 Julius 개발팀에 문의하지 마세요.
