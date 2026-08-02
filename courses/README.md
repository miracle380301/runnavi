# RunNavi 코스 라이브러리

RunNavi 앱이 "내 근처에 어떤 러닝 코스가 있는지" 보여줄 때 읽는 정적 데이터입니다.
서버는 없고 이 저장소의 파일이 전부입니다.

```
index.json              지역 목록 (앱이 내 위치에 걸치는 지역만 골라 받는다)
kr/<지역>.json           그 지역의 코스 요약
gpx/<코스>.gpx           궤적 (코스를 열 때만)
photos/<코스>-N.webp     코스 사진 (대표 750px / 목록용 -thumb 300px)
```

## 라이선스

궤적은 **OpenStreetMap** 데이터에서 뽑았습니다.
© OpenStreetMap contributors, [ODbL 1.0](https://opendatacommons.org/licenses/odbl/1-0/).

사진은 직접 촬영한 것입니다.

## 코스 필드

| 필드 | 뜻 |
|---|---|
| `shape` | `outAndBack` 왕복 · `pointToPoint` 편도 · `loop` 순환 |
| `start` / `end` | 진입점 (다리 이름 또는 역 이름) |
| `river` | 하천 이름 |
| `crossings` | 경로 25m 안의 신호등·횡단보도 수. **실측값이지 가정이 아니다** |
| `pathType` | `footway` 보행로 · `cycleway-adjacent` 자전거길 선에서 뽑음 |
| `pedestrianVerified` | 옆에 보행로가 실제로 있는지 **사람이 가서 확인**했는가 |
| `source` | `auto` 자동 생성 · `verified` 사람이 달려봄 |

`pathType`이 `cycleway-adjacent`인 코스는 자전거길 좌표를 쓴 것입니다.
한국 하천은 보행로가 물리적으로 있어도 OSM에 자전거길 선 하나만 그려진 경우가 많습니다.
둔치에서 두 길은 3~5m 옆에 나란히 붙어 있어 노선·거리·신호등이 같지만,
**자전거길로 달리지 말고 옆 보행로를 쓰세요.**
