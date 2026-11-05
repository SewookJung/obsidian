---
tags: []
created: 2026-03-30 15:44
updated: 2026-03-30 15:44
---

# NPM RUN

[[npm]]은 패키지 관리자고
[[node_module]] 폴더에 [[package.js]] 에 명시된 패키지들이 설치되는걸로 알고 있음

근데 [[dev]] 명령으로 서버를 구동하는데

- npm run dev 했을때 dev 영역에 있는 명세가 서버로 road 되는걸까?
- 실제 운영서버에서 구동은 어떻게 해야될까?
  - python manage.py runserver 같은건 사용하면 안되잖아 gnicorn & nginx를 연동한 사례를 봐야할듯
