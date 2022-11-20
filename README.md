# History-API

브라우저에서 페이지 로딩을 하면, 세션 히스토리라는 것을 갖습니다.
세션 히스토리는 페이지를 이동할 때마다 쌓이게 되며, 이를 통해
뒤로가기 시 이전 페이지로 가거나 뒤로 간 이후 다시 앞으로 가는 등의 이동이 가능합니다.

## pushState, replaceState 두 개의 함수로 화면 이동 없이

현재 url을 업데이트 할 수 있습니다.

## pushState : 세션 히스토리에 새 url 상태를 쌓습니다.

replaceState : 세션 히스토리에 새 url 상태를 쌓지 않고,
현재 url을 대체합니다.

history api
이전 예제에서 hashbang으로 했던 url을 아래처럼 바꿔줄 수 있습니다.

/ -> HomePage
/list -> ListPage
/detail/1 -> DetailPage

## 1. history.pushState

< history.pushState(state, title, url) >

\*state: history.state에서 꺼내쓸 수 있는 값입니다.

\*title: 변경될 페이지의 title을 가리키는 값인 것 같지만 거의 대부분의 브라우저에서 지원하지 않습니다. 빈 string을 넣으면 됩니다.

\* url: 세션 히스토리에 새로 넣을 url입니다.
a태그를 클릭하거나 window.location.href로 url을 변경하는 것과는 다르게 이 url이 변경된다고 해서 화면이 리로드 되거나 그러진 않습니다.
화면의 이동없이 url만 바꿀 수 있다.

## 2. history.replaceState

< history.replaceState(state, title, url) >

\*state: history.state에서 꺼내쓸 수 있는 값입니다.

\*title: 변경될 페이지의 title을 가리키는 값인 것 같지만
거의 대부분의 브라우저에서 지원하지 않습니다. 빈 string을 넣으면 됩니다.

\*url: 세션 히스토리에서 현재 url과 대체할 url입니다.
a태그를 클릭하거나 location.href로 url을 변경하는 것과는
다르게 이 url이 변경된다고 해서 화면이 리로드 되거나 그러진 않습니다.

# 주의해야 할 점

1. History API를 사용해서 SPA를 만들때는 반드시,
   그 특징을 알고 사용해야 한다.

2. replace를 이용하면 페이지 url을 바꾸면서
   이전 페이지로 못들어가게 해야하는 경우에 사용!!

3. npx http-server

4. npx serve-s

5. History API를 사용하는 경우에는 반드시
   404에러 처리를 해주어야 한다!!!
   서버에 응답이 없는 경우에는 다시 루트의 index.html을
   열도록 만들어 주어야 함!!
   npx serve-s는 이러한 처리를 해주는 서버 모듈임!!!
