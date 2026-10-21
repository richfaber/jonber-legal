# project-jonber-legal

존버빌(JonberVille)의 이용약관·개인정보처리방침. GitHub Pages 로 낸다 — https://richfaber.github.io/project-jonber-legal/

**왜 따로 있나.** 스토어는 앱을 안 깐 사람도 열 수 있는 주소를 요구한다. 앱 서버(집)에 두면 서버가 내려갈 때
문서도 내려가 심사 중 반려된다. 본 저장소(project-jonber)는 비공개라 Pages 를 못 쓴다. 그래서 문서만 공개로 뗐다.

**고칠 때 같이 볼 것** — 방침에 적은 숫자는 코드가 지키는 값이다. 한쪽만 고치면 거짓말이 된다.

| 방침의 말 | 코드 (project-jonber) |
|---|---|
| 광장 채팅 30줄 · 60분 | `server/src/config.ts` 의 `chat.keep` · `chat.ttlMs` |
| 신고 1년 · 1,000건, 직전 30분 · 20줄 | `server/src/admin/reports.ts` 의 `KEEP_MS` · `KEEP`, `PlazaRoom` 의 `remember` |
| 금칙어 10분 · 하루 | `server/src/admin/sanctions.ts` |
| 운영 기록은 용량만큼 | `deploy/docker-compose.yml` 의 `logging` |
| 운영 기록의 앱 성능 기록(광장을 옮길 때 프레임 시간) | `app/src/net/perf.ts` · 서버 `PlazaRoom` 의 `perf` 처리 — 보내는 값을 늘리면 여기도 |
| 날씨 지역 — IP 로 22개 도시 중 하나 짐작, 저장 안 함, 날씨 업체에 이용자 정보 안 감 | `server/src/weather/geoip.ts` · `places.ts` · `met.ts`, 클라 `app/src/net/weather.ts`(고른 지역은 기기에 `jonber.place`) |
| 만 19세 이상 · 규칙 동의 | `app/src/ui/Rules.tsx` (규칙 문구를 고치면 `RULES_VERSION` 을 올린다) |

약관·방침을 크게 바꾸면 `Rules.tsx` 의 `RULES_VERSION` 을 올려 다시 동의받는다(약관 제10조).
