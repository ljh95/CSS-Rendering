## Graphics System
- 기본: 점을 찍는 행위
- 가장 복잡하고 어려운 개념
- 각 점의 위치나 크기가 보인다.
- 점을 표현하는 방법: X, Y, Width, Height, Color
- 게임, 벡터그래픽, 포토샵..

### Fixed Number
- 그래픽 시스템에서 고정된 숫자로 표현하는 방법
- 가장 원시적인 시스템

#### 문제
여러 디스플레이에 적응ㅇ해서 그림을 그리기 어렵다.
환경에 적응할 수 없다.
- 해상도
- 실제 브라우저 변경되는 사이즈 
- 스마트폰 가로모드, 세로모드
- Screen Size, Chrome Size

### Abstract Calculator
- %, Left, Block, Inline, Float
- 메타포 = 함수
- 나의 부모, 화면을 기준으로 등등, 
- 실제 화면을 그릴 때 환경에 따라 계산해내는것
- 공식, 수식, 함수
실제 그림을 그리는 순간마다
2단계를 거친다.
숫자 대신에 공식을 거친다.
이 모든 메타포는 그러하다. => 메타포(함수)

함수를 통해 어떻게 기술할지 결정

#### 문제
더 복잡한 무언가를 만들기엔 아직 부족(많이 오래걸림)

### Components
추상화된 그래픽 시스템을 이어받는,공통점을 가진 애들을 만든다.
ex) HTML tag
<img />, 

### Framework
일정한 규칙과 형태를 그리도록 강제한다
ex) HTML 자체


> ### 무언가를 항상 상대적으로 정의한다.(확정적으로 정의하지않고)
IE, Chrome 에서 Windows는 OS이다.
Windows에서 IE, Chrome은 응용프로그램(Application)
>
CSS file, JS file에서 windows는 보이지 않는다.
CSS file, JS file에서 IE, Chrome은 OS이다.
>
항상 상대적인 개념으로 잡힐 수 있다.

### 정리: 점찍는 방법이다.(어떤 방식으로 점을 찍을 것인가?)

## Rendering System
- 그래픽스에서만 쓰이는 것은아니다.
- 어떤 대상을 내가 원하는모습으로 다시 그려내는걸 렌더링이라 한다.
- 복잡한 주파수 패턴을 칼만패턴으로 보이게
- 컴퓨터가 이해하기 편하게 한다.
- 그림을 그리기 위한 데이터를 어떻게 그림으로 바꿔냈는가

- 어떠한 체계를 통해서 그림이 표현되는가?

그림을 표현하기 위한 정보는 무엇인가?

2단계를 통한다.
### 1. Geometry Calculate 박스를 찾는것, 영역을 구분하는것
- ex) reflow
- WebGL, Unity등등 같은 절차

### 2. Fragment Fill 조각을 색칠한다.
- ex) repaint

> 픽셀이란 단어를 쓰지 않는이유
- 중립적이지 않다.
- 핸드폰에서 html 뷰포트는 640으로 나오는데
- 점이 640인가? 훨씬 많다. QHD 등등
- 물리적인 픽셀 4개가 모여 1픽셀을 그린다., 레티나 등등
- 상대적인 개념
픽셀 레티오가 중립적이지 않다.
하지만 우리는 중립적인 단어가 필요하다.
픽셀이 어떻게 되어있는 어떤 추상적인 영역을 다 그려야 하기 때문에
![](https://velog.velcdn.com/images/ljh95/post/a3e1d291-8d12-4034-976b-d4983307ea01/image.png)
1px을 채우는게 중요한게 아니라, 저기 영역의 영역을 다 채워야한다.
언제 모든 공간을 가리키는 단어가 필요하다 - Fragment이다.

## CSS Specifications
CSS는 고정된 숫자를 사용하지 않고, 계산된 체계로 그래픽을 표현할까 와
지오메트리의 영역을 어떻게 표현할까
색칠을 할 때 어떤식으로 명령을 내리까 에 대한 언어

BackgroundColor에 red;
-> 내가 땅따먹기한 영역에 빨간색을 채우라 는 뜻

width, height

%와 숫자까지는 쉽다.
그정도로는 화면을 표현하기 매우 어렵다.

CSS right는 어떤 방식인가?
부모의 width를 계산하고, 자식의 width을 계산해서
부모의 width - 내 width한 값을 내 left좌표로 삼겠다.

추상적인 체걔를 표현하는 방법은 보다 어려운 계산식을 사용하는게 사람에게 더 편할것
부모가 여러층이 있다면 마지막 부모의 가로를 가져와서 내 가로를 뺀다.

내 가로는 무엇인가?
overflow: hidden이 아니라면
overflow: auto라면?
내 가로는 더 늘어난다.
내 width는 더 늘어나게 되어있다.

그럼 그거만큼 재계산을 하게 된다.
'right란 단어 하나에

CSS에선 굉장히 풍부한 추상적인 계산체계를 포함하는 말이 무지막지하게 많다.
각각의 메타포에 대해 내부적으로 어떻게 구현되는지 이해해야지만, 우리가 원하는 레이아웃을 만들 수 있다.

CSS를 배운다.
CSS에 나오는 속성 값이 구체적으로 발현될 때는 어떤 방식으로 계산되어 나오는지에 대해 이해하는것

이런건지 모르니까, 이런 case는 이러니까  copy & paste로 가져다 붙인다
근데, 약간만 변형해달라하면 못한다

하는놈이 있다.
제대로 배운얘들
그런애들은 35이후에 짤린다.

이런 CSS는 어디서 뚝딱 떨어진게 아니다.
렌더링과 그래픽스 분야는 박사학위딴사람들이 열심히 공부해서 만든 오래된 분야이고

그분야의 석학이나 박사들이 다른 시스템의 렌더링 시스템을 차용했다.
웹은 나중에 발현된 학문이기에 기존의 학문을 그대로 받아들인다.

지금도 무지막지하게 들어온다.
-> 체계가 난잡하고 복잡해, 일관성도 없다.

## 사양이 중요한 이유
어떤 부분은 이런 이론에 의해 만들었고, 어떤 관념에 따라 만들었다.
이런 복잡한 체계를 관리하는가?
사양서를 따라 만든다.
사양서가 이렇게 하라했는데, 브라우저가 틀리다면,
브라우저가 틀린 거니까, 해당 브라우저만 예외케이스를 만들면된다.

그러니까 사양서를 보
표준대로 구현하고, 나머지를 폴리필한다.

어떤게 맞는지 알아야 맞게 구현하고 안되는걸 예외처리하기 떄문에

어떤게 옳은지 몰라? -> 우왕좌왕한다.

어디가 표준인지 알아야 한다.

## CSS의 발전 과정
### CSS level 1
Opera browser를 만든 이하닉스가 W3C에 제안했다.
- 야 HTML좋은데 그림과 관련된걸 넣었더니 관리가 안되다.
- 그래픽 시스템 차용해서 CSS라는걸 만드는게 어떨까?


버전을 쓰지 않고 level을 쓴는데 css만그렇다
이때는 A4한개분량

### CSS level 2 + Module
- MS IE4가 세상을 지배해서, 이때스펙은 대부분 MS가 지우너하는게 많다.
이때 그림에 대한건 하나의 스펙으로 관리하느건 무리아니야>

관심있는분야별로 뮤듈을 만들어 모듈별로 스펙을 관리하자.

window의 렌더링 시스템, mac의 렌더링시스템
하나의 단일 사용르로 관리하기 어려원, 상황에 따라 다르게관리하자.

이 시점에 CSS level2가 발표되면 각 모듈화 되었다.

그러면 

### CSS level2.1
여기까지는 CSS level이 존재하는 ㅡ것들
CSS 2.1로 불러도 됨
여기서 이상한 일이생김
어떤 분과는 일을 열심히해서, module3를 발표하는 팀이 생김

나중에 깨달ㅇㅁ
어떤 스펙은 굉장히 많이 버전업이 활잘하게 되는데,
어떤 스펙은 레밸업 할 일도 없고, 하지도 ㅇ낳구나
CSS3는 아놀수 있을 까? 없을까?

모든 모듈이 꼭 발전해야할 필요가 있는 것은 아니기 때문에, CSS3라는것은 나올 수 없구나
CSS2.1이후에 CSS level3로 가는게 불가능핟다.

그래서 2.1때 이미 모듈들이 레벨 3가 된다.
CSS3란, CSS2.1에 포함된 모듈들중에 레백 3인것을 CSS3라 부르고
> Syntax 3, Cascade 3, Color 3, Selectors 3, Background 3, Values 3, Text 3, Text Decor 3, Fonts 3, UI 3

모듈레벨이란 것으로 바꾼다.
이후 새로 생긴 CSS
> Transforms 1, Compositng 1, Effects 1, Masking 1, Flexbox 1, Grid 1

애네들은 CSS Module Transforms level 1이다.

실제 사용서를 보면
이젠ㄴ 애네들이 각자 레밸업하는 것


모듈은 모듈나름대로 업데이트 하고 있다.
모듈마다 업데이트하는 간격이 다르다.
![](https://velog.velcdn.com/images/ljh95/post/d071c858-b2fc-4704-903a-5ecf06e49a7f/image.png)

기존 사용서도 다 다시 바뀐다. 다른게 바뀌면 다른것도 영향을 받을 수 있기 때문에

이 글미을 
이 CSS 가 난잡하고 어려운 이유는 MS가 일을 안해서가 아니라 이런 배경이 있기 때문이다.
CSS가 사양이 이따구로 되었기 때문에 브라우저가 전부 최신사양을 따라가기 어렵기 때문이다.

브라우저가 level1을 지원하고 있게지, 하지만 level2도 지원하는건지? 봐야한다.

브라우저 셀렉터 스펙은 level1
I11dms level2이다.

어떤 스펙이 궁금하면 W3C에서 recomandation을 보면된다.

CSS3, CSS4가 있다고 하면 안됨

이 세상이 여기서 끝나면 좋은데, 
W3C가 영향력이 쎈 시기는 아이폰 전 MS집권하에 있을 때
이후에는 구글과 아이폰의 힘이 강해졌다.
 
W3C에 새로운 신흥강자가 반발하기 시작
그러면서 W3C도 많은걸 내려놓음

W3C에 draft로 제안하고, 브라우저가 먼저 구현해도 뭐라 안그럴게
그전엔, W3C에 권고안이 되어야만 브라우저가 개발하는게 맞지 이랬는데,(통제)

크롬 최신 기술은 W3C권고안이 아니라, 대부분 draft이다.
나 이거 구현하고싶은데? 막 구현한다.
권고안은 구현하지 않은게 많다.
W3C중앙 파워가 굉장히 약해졌다.

W3C에서 이걸 인정하면서 [W3C community and buisiness group](https://www.w3.org/community/)이란걸 우녕ㅇ하기 시작

W3C 커뮤니티 그룹에서 그룹을 만들고 사용을 만드러서 W3C에 draft로 밀어넣는다.
그리고 브라우저는 만들고, 무시하고 그럼

구글 애플 삼성이 그룹 만들고, 자기 스펙을 맞춰서 자기 브라우저에 넣으면 끝
실제로 이렇게 돌아감
CSS에 영향력이 큰 그룹이 있는데
그게 WICG 구글이 주축이다.

이들은 크로미윰에 먼저 반영하고, W3C에 draft를 날림


### 현재 브라우저 스펙을 관리하려면

이런 사양들 때문에 현재 브라우저 스펙을 따질려면, 더 많은 단체들과 더많은 기업들의 스펙을 따라야한다.
W3C 레커맨데이션에서 구현되지 않을 가능성이 큰데, WICG에서 드래프트로 만들어진 기능들은 브라우저에 포함될 가능성이 크다.

최신 브라우저 트렌드는 WICG에 가깝다고 볼 수 있다.
스펙의 변화, 표준의 변화도 예의 주시할 필요가 있다.


---

# CSS
## Normal Flow(고유명사)
- 오늘 처음 배울 내용
> 양키 학문의 두번째 문제점
고유명사를 일반 명사로 정의한다.
이게 일반명사 같다라고 느껴지지만 사실 고유명사인다.
일반명사에 고유명사뜻을 부여해버림
ex) 도메인
일반인: 우리집 마당. 영역, 마당
개발자: 인터넷 IP를 대신하는 이름
도메인은 고유명사가 되버림
ex) 프로토콜
일반인: 계약서, 합의서
개발자: ...
>
일반명사처럼 보이는 고유명사르 잘 알아차려야한다.
번역가능하기 매우 힘들다.
그 말이 사실 일반명사가 아니기 때문에 굉장히 힘들다.

- visual formatting model
positionng schems & normal flow

### Position
static, relative, absolute, fixed, inherit

아까 그래픽 시스템에서 추상적 개념 시스템 
- 어떤 지오메트리에 left, top를 결정할 때 사용하는 추상적인 개념 체계
- width, height, left, right 결정할 때, 결정하는 시스템
계산 공식

계산하는 공식
left, top 계산 식이 틀려진다.

근데 normal flow는 static, relative일 때만 적용된다.
그리고 2가지로 설명된다. (2가지 계산 공식이 있다.)
- block formatting context(BFC)
- inlint formatting context(IFC)
- relative positioning(이불이긴 하지만 포지션 모델에서 계산된다.)

### BFC
block: 부모의 가로길이를 가득 채운 단위, 한 줄을 다먹은 행
block formatting context: 한줄을 다먹을 떄 어떤식으로 곘나하나? x는 언제나 0, width은 부모의 width

다음 block이 나올때 다음 y는 어딘가?
첫 번째 block의 height가 다음 block의 y값이다.
이 계산 방법이 BFC이다.

2번째 특성
안에 있는 Block요소의 height의 합이 나의 Height가 된다.
기본 작동

IFC는 인라인인데 나의 컨텐츠 크기만큼 가로를 차지한다.
또한 동시에 그 다음번 요소의 IFC는 첫번째 width이후에 left값이 놓여진다.

애네들은 인라인 요소의 합이 창을 넘어가면 부모의 가로를 넘어가면 내려간다.
지금 요소들중 가장 큰 height가 line-height로 계산되어 그 이후가 높이가 된다.

인라인을 요소중 가장 큰 baseline
그런 개념이 생긴다.
인라인 안에 잇는 개념 baseline
용어가 어려워 그얼지
한줄이 그려지는디, 원리

근데 IFC가 생겨나도, block이 생기면 그 즉시 바로 BFC영역이 계산된다.

![](https://velog.velcdn.com/images/ljh95/post/40f0fc39-0636-4cba-8109-565ea78cc0aa/image.png)
특별하게 width를 주어도 
block이기 때문에, 이 옆에 공가니 있어도 밑에 내려간다.
예가 width가 500이란 뜻은 geometry에 fragment가 500만큼이란 뜻이지
실제로는 여기까지다
![](https://velog.velcdn.com/images/ljh95/post/9de9b57c-fe7b-4a84-89b5-bd478dbcb4df/image.png)

부모의 영역을 다 먹는데, fragment만 여기까지로 정의한거지
width를 얼마를 먹이든 쓸 수 없다.
\
![](https://velog.velcdn.com/images/ljh95/post/af9e5333-41a3-413a-9c8f-cfa154c71a77/image.png)
부모의 영역을 뚤고 가냥
이걸 엔터를 치게 만들려면 

그건 물론 div가 size를 auto로 줬기 떄문인다.
ifc인데 아래로 안내려가고 부모의 width를 뚫고가냐
a를 끊어 놓으면 아래로 내려간다.
a를 붙이면 뚫고가고, 
암묵적으로 html이 그림을 그릴 때, 공백 문자가 없는 문자열을 하나의 IFC영역으로 보는것
엔터가, 스페이스가 주면 하나의 span태그 영역이 되어버린다.
하나의 인라인이 되어버린다.
공백문자를 삽입해야해 
그게 싫으면 붙여있는 인라인을 뽀개버리고 싶다면, word-breaking 속성을 줘야한다.
주지 않으면 기본적인 html문법에서 공백문자가 없는 문자열을 하나의 인라인 태그로 본다.

![](https://velog.velcdn.com/images/ljh95/post/311d3751-3c0c-4d6c-896e-9c5ecab68f00/image.png)


```html
<div style="width:200px;background-color: red;">
  aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
</div>

<br>
<div style="width:200px;background-color: red;">
  aaaaaaaaaa
  aaaaaaaaaaaaa
  aaaaaaa
</div>
<br>
<div style="width:200px;background-color: red;word-break: break-all;">
  aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
</div>
```

이 공간 안에서 공백문자 없이 붙어 있는 문자열도 하나하나 인라인태그롤 인식해라 라는 뜻이다.
그러기 때문에 자동으로 엔터가 쳐진다.
경계면에서 엔터가 처지는게 아니라
공백문자로 인라인을 구분했는데, 워드브레이킹을 주면 단어하나하나를 다 인라인으로 봐라라느뜻이다.
당연히 더 느리게 된다.
브라우저 전역속성으로 워드 브레이킹을 주게되면 굉장히 느려지게 된다.
왜냐면, 덩어리를 하나의 geometry로 계산했는데,

word-breaking을 주면 글자 하나하나에 다 geometry를 계산하게 되기 때문이다.
급 느려진다.
아까 지오메트리를 계싼해 색깔을 칠한다했는데
work-breaking을 그냥 주면 아노딘다.

a 하나단 인라인 요소 하나로 계산하기 떄문
wordbreaking을 주면 width에 맞춰 끊어지는 원리

![](https://velog.velcdn.com/images/ljh95/post/01b2b6ee-e460-497c-9fda-f7ba18be4dfb/image.png)
```html
  <div>HELLO
    <span>WORLD
      <div style="background-color: red;">&nbsp;</div>
    </span>
    !!
  </div>
```
![](https://velog.velcdn.com/images/ljh95/post/208ff613-2d74-4022-b349-4254d47f8068/image.png)

렌더링 시스템에 대한 이해가 없기 때문
렌터딜ㅇ 시스템과 돔의 포함관계는 다르다.
렌더링은 BFC, IFC로 그린다.
돔의 포함관계는 이렇게 보일지 몰라도
렌더링기준은 BFC(width:500) -> IFC(HELLO) -> IFC(WORLD) -> BFC(bg-red, &nbsp;) -> IFC(!!)

태그의 구조가 렌더링 구조랑 일치하는게 아니다.
![](https://velog.velcdn.com/images/ljh95/post/c8b3e9e3-9bb5-40b0-ac00-8947714b1042/image.png)

```html
  <div style="width: 500px;">
    **
    <span>HELLO
      <span>WORLD
        <div style="background-color: red;">&nbsp;</div>
      </span>
      !!
      <div style="background-color: blue;">&nbsp;</div>
    </span>
    **
```

여기서 relative를 넣으면 relative모델을 먹게된다.
static으로 그렸는데, 상대적으로 위치를 이동시켜
그러면 static으로 그린 후에 상대적으로 relative만큼 이동시키면 된다.

월드와 빨간색 박스를 를 이동시키면 그렇게 그래야하지 않나?
실제로 그렇게 그려진다.
![](https://velog.velcdn.com/images/ljh95/post/3cd61b94-0513-4f6a-b69c-d6d17683789b/image.png)

```html
  <div style="width: 500px;">
    **
    <span>HELLO
      <span style="position: relative;top: 50px;">WORLD
        <div style="background-color: red;">&nbsp;</div>
      </span>
      !!
      <div style="background-color: blue;">&nbsp;</div>
    </span>
    **
  </div>
```
이 그림이 이해가 된다.

근데 position static과 relative가 겹치면 relative가 무조건 위로 올라간다.
Relative 끼리는 z-index경합을 벌이지만, static과 relative가 만나면 relative가 무조건 위로 뜬다.

geometry계산은 static 속성으로 계산이 된거다.
그것이 relative의 의미

relative란,  staic으로 그린 다음에 relative하게 옮겨주면 된다.

normal flow를 설명하려면 이렇게 설명한된다.
BFC, IFC, relative까지가 normal flow에 포함된다.

가장 많이 그림을 그려지는 공식이 이 normalflow이다.

내가 div를 쓰명 글자가 밀려날꺼다 > 가장 많이 쓰여지는 공식

normal flow하에서만 자동으로 width계산되고, height계산되고,위치 잡아주는 것
normal flow를 벗어난다면(position: absolute, fixed, inhrit) 이런 자동으로 해주었던 width, heigth, 위치값 계산이 벗어나지는 것

