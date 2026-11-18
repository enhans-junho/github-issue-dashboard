# GitHub 이슈 모니터

GitHub 저장소의 이슈를 주기적으로 불러와 보여 주는 단일 페이지 대시보드입니다.

- 주소: https://enhans-junho.github.io/github-issue-dashboard/
- 특정 저장소를 바로 열기: `https://enhans-junho.github.io/github-issue-dashboard/?repo=<조직>/<저장소>`

## 동작 방식

- 이슈 데이터는 이 저장소에 없습니다. 페이지를 연 사람의 브라우저가 본인 토큰으로 `api.github.com`을 직접 호출합니다.
- 토큰은 그 사람의 브라우저(localStorage 또는 sessionStorage)에만 저장되고 다른 곳으로 보내지 않습니다.
- 새로고침 주기: 10초 ~ 10분 또는 끄기. 변경이 없으면 ETag 304로 처리되어 인증 요청 한도를 거의 쓰지 않습니다.

## 토큰

- Fine-grained 토큰 권장: Resource owner = 대상 조직, Repository access = 대상 저장소만, Permissions = **Issues: Read-only**
- Classic 토큰은 `repo` 범위가 필요하고, 조직에 SAML SSO가 있으면 SSO 승인이 필요합니다.

`<계정>.github.io` 아래의 다른 프로젝트 페이지와 브라우저 저장소를 공유하므로, 공용 PC에서는 「토큰을 기억」을 끄고 쓰세요.
