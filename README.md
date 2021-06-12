# miniProject
# group 34
[MO:PEN_기획서](https://www.notion.so/MO-PEN_-6c78bdd9190c4319ad390d301f2e69a9)

# 1. 웹사이트 링크

---

[MO:PEN](http://mo-pen.shop)

# 2. 제목

---

### **MO:PEN**

# 3. 프로젝트 설명

---

### **개요**

우리 모두의 펜션 **MO:PEN,** 전국의 펜션 정보들을 지역별로 찾아보세요! 

직접 평점과 리뷰를 남기고, 다른 사람들과 공유할 수 있습니다. 관심있는 곳은 담아 두었다가 항해가 끝나면 훌쩍 떠나 보는 건 어떨까요?

### 주요 기능

- 회원가입 / 로그인
    - 회원가입을 하고 로그인을 한 후에 사이트 이용이 가능합니다.
    - 중복되지 않는 id로 가입 가능합니다. 비밀번호는 형식에 맞게 생성해야 합니다.
    - 로그인 시 암호화 된 비밀번호가 기존 등록된 것과 맞는지 확인합니다.
    - 맞을 경우 사용자는 사용자의 정보가 담긴 토큰을 발급 받고 로그인 할 수 있습니다.
- 메인페이지
    - 전국의 펜션 리스트를 볼 수 있습니다.
    - 펜션 정보를 지역별로 나누어 볼 수 있으며,
    - 또한 가격순, 평점순으로 정렬할 수 있습니다.
- 상세페이지
    - 펜션의 가격 정보와 별점을 확인 할 수 있습니다.
    - 댓글을 달아 다른 사람의 리뷰를 확인 할 수 있습니다.
    - 사용자의 즐겨찾기 목록에 해당 펜션을 저장할 수 있습니다.
- 마이페이지
    - 사용자가 기존에 담아 둔 즐겨찾기 목록을 불러옵니다.
    - 사용자의 목록이 없을 시, 즐겨찾기를 추가 해 보라는 문구가 나옵니다.
    - 이미 저장된 즐겨찾기는 삭제 할 수 있습니다. 중복 추가는 불가능합니다.
- 와이어프레임 / 테마 색상

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8ed08f87-fda9-4ef3-b945-17a06d0cb16c/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8ed08f87-fda9-4ef3-b945-17a06d0cb16c/Untitled.png)

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/da13f070-3302-4f9e-854b-66b415ec66f9/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/da13f070-3302-4f9e-854b-66b415ec66f9/Untitled.png)

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/798b2417-f67d-40ac-b2af-3f3e9ad2d06d/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/798b2417-f67d-40ac-b2af-3f3e9ad2d06d/Untitled.png)

### 🔥프로젝트 진행하며 배운 것🔥

- SSR (Server Sides Rendering) 장점
    1. 완성된 페이지의 형태로 응답되기 때문에 검색엔진에 최적화 가능합니다.
        - 빈 html을 전달하는 클라이언트 렌더링은 검색 엔진에 잘 잡히지 않지만 이미 서버에서 렌더링 된 html 파일을 보내주기 때문에 검색 엔진에 잘 잡힙니다.
        - 전통적인 웹 애플리케이션은 서버 사이드 렌더링 방식을 사용합니다.
    2. 서버 사이드 렌더링 방식은 첫 렌더링 된 html 파일을 클라이언트에게 전달해 주기 때문에 초기 로딩 속도를 많이 줄여줄 수 있습니다.
        - 클라이언트 사이드 렌더링의 경우 서버는 json 파일만 보내고 자바스크립트가 html을 그리는 역할을 담당하기 때문에 초기 구동 속도가 느립니다.
- JWT 방식의 장점
    1. 서버가 session을 저장하고 관리할 필요가 없습니다. 
        1. client에게 token을 발급하고 client가 준 token이 올바른지만 확인하고 맞는 경우 권한을 줍니다. 따라서 사용자 인증에 필요한 모든 정보는 토큰 자체에 포함하기 때문에 **별도의 인증 저장소가 필요 없습니다.** 
        2. session의 경우 서버에 session id를 저장하여 관리. 서버가 많은 경우 session 데이터베이스를 따로 만드는데 이를 관리하는 과정이 복잡하고 데이터베이스에 부하가 올 수 있습니다.
    2. 토큰을 기반으로 하는 다른 인증 시스템에 접근이 가능합니다.
        1. google, facebook도 jwt 인증 방식을 사용합니다. 페이스북, 네이버 등의 서비스를 통해 로그인할 때 토큰에서 사용자의 정보를 선택적으로 가져올 수 있습니다. 
        2. token 기반이기 때문에 secret key를 통해 token을 hash 하여 암호화하기 때문에 secret key는 최대 한 시간에서 몇 분마다 새로 바꾸도록 코딩하는 게 좋습니다. **token의 보안에 대해서 생각을 해야 합니다.**

# 4. 데모영상 유튜브 링크

---

[펜션 정보를 한 눈에 보는 사이트가 있다고? 모두의 펜션!?](https://youtu.be/ZZpLt255E6c)

# 5. 데모영상 썸네일 (280*160)

---

# 6. Git Repository (github)

---

[Hanghae99-Team34-1stWeek/miniProject](https://github.com/Hanghae99-Team34-1stWeek/miniProject)
