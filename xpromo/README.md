# HYPERSPEED 앱 목록 (각 앱 설정 「HYPERSPEED의 다른 앱」)

각 앱 설정 맨 아래의 가로로 넘기는 한 줄이 이 `apps.json` 을 읽어 **자기 자신을 뺀** 앱을 보여 준다.
여기만 고치면 모든 앱에 반영된다(앱 다시 출시 필요 없음). 앱은 마지막으로 받은 목록을 기억하고, 못 받으면 앱 안에 넣어 둔 목록을 쓴다.
공용 코드: Mac `~/IdeaProjects/_xpromo/xpromoApps.ts`.

## 새 앱 넣기

1. `apps` 에 한 줄:
   - `kind` — 소문자 · 숫자 · `_`, 24자까지 (GA4 `xpromo_open` 의 kind 값)
   - `ios`(App Store 숫자 ID) · `android`(패키지) — **나와 있는 쪽만**. 없는 쪽 기기에선 안 보인다.
   - `name` — 스토어 이름. `en` 필수 + 언어별(`ko` `ja` `zh-Hant` …)
   - `short`(선택) — 카드 밑 짧은 이름. `all` = 모든 언어, 언어별로도. 없으면 `name`
   - `newUntil`(선택) — `"2026-12-31"` 처럼, 그날까지 **NEW 표시 + 맨 앞**
   - `only`(선택) — 그 언어에서만 보임. 한국어만 되는 앱은 `["ko"]`
   - `icon` — `https://hyperspeedgames.com/xpromo/<kind>.webp`
2. 아이콘 `xpromo/<kind>.webp` (144×144) 올리기.
3. 커밋 · 푸시 → 몇 분 뒤 반영 → 앱은 다음에 설정을 열 때 받는다.

순서: NEW 앱이 맨 앞, 나머지는 **하루마다 섞인다**(그날 안에선 그대로). 12개까지만 읽고, 형식이 틀린 줄은 앱이 건너뛴다.
빼기: 줄을 지우면 된다.
