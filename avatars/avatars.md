<h1>5월3일 과제</h1>

## float 을 사용하여 레이아웃 구현하기

### 1단계 마크업 구조를 파악해 레이아웃 구현하기

1. 8개의 프로필을 넣을 div 박스
   **aria-label=profiles 으로 접근성 높이기,class="profiles 선택자 주기**
2. 컨텐츠img div박스 class="profile1 profile-group" 두가지 클레스 주기
3. alt="profile1..2..3" 으로 각각 할당
4. class="profile1 profile-group" 안에 컨텐츠 img 주기 3번째 이미지 없어서 내사진으로 대체..ㅎㅎ
5. span테그를 이용해 온라인 오프라인 표시로 사용할 태그

---

### 2단계 마크업 구조에 CSS 입히기

1. img태그 width,height 64px border-radius: 50%; 주기
2. 이미지 간격 20px 로
   **각 div 박스마다 margin:10px씩 부여해 양쪽으로 20px** 로 간격주기
3. 이미지를 감싸는 div 박스에 padding:10px 할당하여 양쪽 끝에 이미지 모두 20px 씩 간격주기,
4. 이미지를 4개씩 정렬하기 위해 margin을 포함하여 84\*4=336width height=168 을 할당
5. 이미지가 들어있는 박스에 float:left 할당하여 가로로 마크업 순서대로 정렬
6. profiles div:nth-child(-n + 8) {
   position: relative;
   } 로 profiles 안에 자식 div 모두에게 position: relative 를 부여하여 온라인 마크가 해당 div를 기준으로 이동하게 함
7. online,offline 컴퍼넌트를 두개 만들어 position: absolute; 를 부여함 right , bottom 으로 이미지 위에 온오프라인 마크 올려주기

---

### 3단계 supports를 이용해 flex가 가능한 브라우저에 값 할당하기

1. profiles 에 display:flex 를 주어 컨텐츠박스를 flex로 만듬
2. flex-flow 에 기본값인 row를 주고 박스 범위가 넘어가면 줄바꿈 될수있도록 wrap 으로 바꿔주기
3. flex-container 안에 flex-item 은 order속성으로 순서를 바꿀수 있음
4. .profiles div:nth-child(-n + 4) {
   order: 1;
   }
   로 앞 4개의 자식에게 order:1 부여 하여 뒤쪽으로 순서대로 정렬하게함 order 디폴트값 = 0
