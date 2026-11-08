# farm-remote-config

세 판매 앱(ImageFarm·OmniVideoFarm·VideoFarm)과 운영앱이 같이 읽는 **서명된 원격 설정**.

- `remote-config.json` — 앱이 읽는 서명본(`{ payload, sig }`, ed25519). 앱이 받는 주소: `https://raw.githubusercontent.com/japing81/farm-remote-config/main/remote-config.json`
- `remote-config.source.json` — 서명 전 원본(사람이 읽는 값)
- 바꾸기: Actions `sign-remote-config` 를 [Run workflow] 로(원본 JSON 전체를 붙여 넣는다 — `issuedAt` 은 지금 시각으로 바뀐다). 개인키는 저장소 비밀 `REMOTE_CONFIG_PRIVATE_KEY` 에만 있다.
- Flow api 스위치(`killSwitch.flowApi`)는 운영앱 관리 > Flow 계정 "Flow api (원격 설정)" 에서 바꾼다(같은 workflow 를 부른다).

절차·스위치 뜻은 소스 저장소 `docs/runbooks/google-change.md` §2.
