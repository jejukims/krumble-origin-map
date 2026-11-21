# KRUMBLE ROASTERS · Origin Map

크럼블 로스터스 매장에서 쓰는 커피 산지·농장 지도입니다. 손님이 커피 이름을 누르면
그 커피가 자란 산지와 농장이 세계 지도 위에 표시됩니다. 파일 하나(`index.html`)로 동작합니다.

**바로 보기: <https://jejukims.github.io/krumble-origin-map/>**

## 기능

- **라인업 카드** — 매장에서 쓰는 커피를 산지·농장·고도·품종·가공 방식과 함께 소개
- **지도** — 카드를 누르면 해당 농장으로 지도가 이동하고 핀이 표시됨
- **자유 검색** — 내장 데이터(산지·농장 48곳 / 26개국)에서 먼저 찾고, 없으면 실시간 지오코딩으로 후보를 찾아 `LIVE` 카드로 표시
- **딥링크** — `?coffee=<id>` (예: `?coffee=el-diamante`), `?q=<검색어>`
- 모바일 화면 대응

## 직접 실행하기

파일 하나라서 별도 빌드가 필요 없습니다.

```bash
python3 -m http.server 8000
# http://localhost:8000/
```

## 사용한 외부 자원

| 용도 | 서비스 |
|---|---|
| 지도 라이브러리 | [Leaflet](https://leafletjs.com/) 1.9.4 (unpkg) |
| 베이스맵 | Esri Light Gray Canvas (키 없이 사용) |
| 글꼴 | [Pretendard](https://github.com/orioncactus/pretendard) (jsDelivr) |
| 주소·지명 검색 | Nominatim, Photon |

## 데이터에 대하여

산지·농장 좌표는 공개된 지명 좌표와 농장이 공개한 GPS를 기준으로 넣었습니다. 카드의
배지로 근거 수준을 구분합니다: `CRUMBLE LINEUP`(매장 사용 확인) / `대표 농장` /
`대표 산지 · 예시 데이터` / `LIVE · 실시간 검색`.
컵노트는 공급사·로스터 표기를 조합한 것으로, 실제 컵핑 기록에 따라 달라질 수 있습니다.

## 상태

프로토타입 v0.1. 외부 무료 서비스(Esri 베이스맵, Nominatim)에 의존하므로, 상시 공개
서비스로 운영할 때는 키 기반 타일 제공자로 바꾸는 것을 권장합니다.
