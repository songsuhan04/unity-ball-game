# ⚽ Ball Rolling Game (EXGame)

공을 굴려 맵에 흩어진 아이템을 모두 모은 뒤 골 지점에 도착하면 다음 스테이지로 넘어가는 **3D 퍼즐 액션 게임**입니다.
고등학교 때 Unity 3D 물리와 게임 루프 구조를 익히기 위해 만든 프로젝트입니다.

> 작업 시기: 2022년 (고등학교 재학 중) · Unity 2021.3.11f1 · C#

## 🎮 조작법

| 키 | 동작 |
|---|---|
| `W` `A` `S` `D` / 방향키 | 공 이동 |
| `Space` | 점프 (바닥에 닿아 있을 때만) |

- 스테이지의 **모든 아이템을 모은 상태**로 골 지점에 도착하면 다음 스테이지
- 아이템이 부족한 채로 도착하거나 맵 밖으로 떨어지면 **현재 스테이지 재시작**
- 마지막 스테이지를 클리어하면 처음으로 돌아갑니다

## ✨ 구현 내용

| 스크립트 | 역할 |
|---|---|
| [`PlayerBall.cs`](Assets/Script/PlayerBall.cs) | `Rigidbody.AddForce`로 이동·점프, 바닥 태그로 **이중 점프 방지**, 아이템 획득·골 판정 |
| [`GameManagerLogic.cs`](Assets/Script/GameManagerLogic.cs) | 스테이지별 총 아이템 수 / 획득 수 UI 표시, 낙하 감지 시 스테이지 재시작 |
| [`CameraMove.cs`](Assets/Script/CameraMove.cs) | 플레이어와의 오프셋을 유지하며 `LateUpdate`에서 카메라 추적 |
| [`Itemcan.cs`](Assets/Script/Itemcan.cs) | 아이템을 월드 Y축 기준으로 회전시키는 연출 |

- 씬 3개(`Example1_0` ~ `Example1_2`)로 구성된 스테이지
- 태그(`Player`, `Item`, `Point`, `Floor`) 기반 충돌·트리거 처리
- TextMesh Pro / UI Text로 HUD 구성

## 📦 다운로드

[Releases](../../releases)에서 Windows 빌드(zip)를 받아 압축을 풀고 `EXGame.exe`를 실행하세요.

## ▶️ 프로젝트 열기

1. Unity Hub에서 **Unity 2021.3.11f1**(또는 2021.3 LTS) 설치 후 이 폴더 열기
2. 효과음은 Unity Asset Store의 무료 에셋 **Casual Game Sounds**를 사용했습니다.
   에셋 라이선스상 저장소에는 포함하지 않았으므로, Package Manager → *My Assets*에서 받아 `Assets/CasualGameSounds`에 임포트해 주세요.
3. `Assets/Scenes/Example1_0`을 열고 ▶ Play
