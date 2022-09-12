[< 뒤로가기](./README.md)

## 개발팀 Git 룰

```CMD
1. 브런치 전략
1.1. 사전 정보
1.2. Git Flow 전략 선택
2. 브런치 명명규칙
3. 커밋 명명규칙
4. ISSUE, PR, *pull request* 명명법
```

### 1. 브런치 전략

#### 1.1. 사전 정보
    
- 선아님 : `develop` 와 `feature/login` , `bugfix/login` 브런치를 PR 하고 완료 시 삭제
    
- 원석님 : 위와 동일
    
- 창용님 : `submain` 과 `dev/작업자명` 유지 한 상태로 지속적으로 PR 을 한 것
    
- 민석님 : `develop` 와 `feature/login` , `bugfix/login` , `refactor/login` , `module/testing-lib` 
    
- 승근님 : 위와 동일    

#### 1.2. Git Flow 전략 선택

- 참고 링크 : [https://overcome-the-limits.tistory.com/7](https://overcome-the-limits.tistory.com/7)

```jsx
목적에 맞는 브런치 생성

해당 브런치에서 작업 진행
해당 브런치에서 작업 완료 시 PR 을 통해서 develop 으로 병합
병합 이후에는 해당 브런치 삭제
```

`package-lock.json` 이 충돌이 나실 때,

마지막에 `npm i 모듈명` 하신 분의 `package-lock.json` 에서 **기존의 모듈들** 은 그대로 있고 추가로 **설치한 모듈** 만 달라집니다.
그래서, `npm i` 를 해버리면 **모든 모듈** 이 업데이트가 되기 떄문에 가장 안정적인 버전이 `npm i 모듈명` 를 한 사람의 로컬 PC 에 있는 package-lock.json 이 최신입니다.

```jsx
선아님이 npm i axios 를 진행
창용님이 npm i 를 해서 package-lock.json 이 달라지거나 충돌이 났을 경우
창용님은 충돌난 시점에
	선아님의 package-lock.json 전달 받으시고 충돌난 파일 다 지우고 덮어씌우시면
	문제가 해결됩니다.
```

### 2. 브런치 명명규칙

- main
- develop
- feature/기능명~컴포넌트명
- bugfix/기능명-컴포넌트명
- module/모듈-목적
    - 단수의 경우라면 해당 모듈의 이름
    - 복수의 경우라면 공통된 특징
- refactor/기능명-컴포넌트명
    > Refactoring 이란? <br>
    > 간단하게만 표현하면, 돌아가게 만들어놓은 코드를 여러 가지 이유로 같은 기능을 하되, 조금 더 좋은 방식으로 고치는 작업 <br>
    > 더 정확한 표현은 구글링을 통해서 확인해봅시다!

### 3. 커밋 명명규칙

- Create 파일 생성
- Update 파일 수정
- Delete 파일 삭제
- `Refactor` 대상과 목적
- `Bug-Fix` 대상과 목적
- `Docs` : 문서작업 `[README.md](http://README.md)` 같은 것을 수정 했을 때, …
- `Comment` : 주석 `//` 생성 하거나 수정하는 것 작업 만 진행하실 때, …

### 4. ISSUE, PR, *pull request* 명명법

- 버그 리포트
    
```jsx
    ---
    name: 버그 리포트
    about: 한 일 / 에러 내용 / 조치 사항
    title: 'Bug : 버그 주요 키워드'
    labels: 'bug'
    assignees: ['unchaptered', 'sumin-dev', 'subeom-lee']
    ---

    ### 한 일

    로그인 기능 구현을 했습니다.

    ### 에러 내용

    ```cmd
    에러 내용
    ```

    ### 조치 사항

    만약 조치한 것이 있거나 구글링한 게 있다면, ...

    ### 환경 설정

    ```cmd
    OS:
    Node: 16.15.1(unchpatered) 16.16.0(sumin-dev, subeom-lee)
    npm : 8.1.1(all)
    ```
```
    
- 문서 리포트
    
```jsx
    ---
    name: 문서 작업
    about: 특이한 기술 문법 / 간단한 소개 + URL
    title: 'Docs : 소개글'
    labels: 'documentation'
    assignees: ['unchaptered', 'sumin-dev', 'subeom-lee']
    ---

    ### 한 일

    로그인 기능 구현을 했습니다.

    ### 환경 설정

    ```cmd
    OS:
    Node: 16.15.1(unchpatered) 16.16.0(sumin-dev, subeom-lee)
    npm : 8.1.1(all)
    ```
```
    
- PR 양식
    
```jsx
PR : 변경사항 `변경파일`
```