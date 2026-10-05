# FIGXY ad content

FIGXY 앱 HOME 화면 광고 배너(사이트 로고 + 링크)의 **공개 runtime 데이터**만 두는 저장소입니다.

- `ads.json` — 광고 목록 (`schemaVersion: 1`)
- `logos/` — 배너 로고(PNG/WebP)

## 상태

- 현재 내용은 **샘플/테스트 데이터**입니다(실제 상업 광고가 아님). 링크는 `example.com`입니다.
- FIGXY release 앱은 아직 이 저장소를 읽지 않습니다(원격 연결은 다음 단계).

## 규칙

- 앱 소스 코드·비밀정보(토큰·키·비밀번호)·개인 데이터는 두지 않습니다.
- 앱이 로그인 없이 읽을 수 있도록 public으로 유지합니다.
- 편집·게시는 FIGXY Ad Manager로 합니다(게시 1번 = commit 1개, force push 없음).
- 되돌리기: 문제가 된 게시 commit을 `git revert`합니다.

## ads.json (schema v1)

```json
{
  "schemaVersion": 1,
  "enabled": true,
  "updatedAt": "2026-10-05T13:30:00+09:00",
  "banners": [
    {"id": "shop-a", "name": "SHOP A", "logo": "logos/shop-a.png",
     "url": "https://example.com/", "enabled": true, "order": 1}
  ]
}
```

- `enabled: false`(전체) → 앱에 광고 없음. 배너별 `enabled: false` → 그 배너만 숨김.
- `order` 오름차순으로 표시. `url`은 http/https만.
