# Login 과제

## 목차

1. [과제 조건 확인](#과제-조건-확인)
1. [과제 진행 과정](#코드-주요-설명)
1. [결론과 회고](#결론-및-문제점)

## 과제 조건 확인

- 로고 이미지는 `<svg>` 요소로 마크업 할 것

  SVG-VIEWER EXTENSION을 추가하여 SVG 파일을 VSCode에서 서브뷰로 확인하며 작업했다.

- 웹접근성을 고려하여 로그인 폼 서식을 마크업 할 것

  (레이블 제공의 경우 WAI-ARIA가 아닌 HTML 네이티브 방식으로 구현)

  -aria-required를 폼 서식으로 사용하지 않을 것

- 아이디와 비밀번호는 필수 입력 서식임을 알 수 있도록 구현할 것

  `input`태그의 `required` 속성을 사용하면 지정하지 않을 시 form이 제출되지 않는다.

- IP 보안 텍스트 클릭 시 미리 제공 된 pages/ip_secruity.html 파일이 새창에 열리도록 구현할 것

  linker 태그인 `a`태그를 사용하여 `link`속성에 상대 경로를 지정함

- 로그인 상태 유지와 IP 보안 ON/OFF UI는 마우스 이외에 키보드로도 조작 가능하도록 구현할 것

  여러 div 요소를 부모로 묶고 tableindex 속성을 사용하면 키보드 접근성을 고려하기 용이할 것이다.

## 과제 진행 과정

### login

`div` 태그를 이용하여 하위 요소들을 login의 이름으로 묶었다.
결과물의 짜임새를 봤을 때 하나의 컴포넌트로 재활용할 수 있을 확률이 높아보였기 때문이다.

### login\_\_title

BEM방식을 통해 login인의 하위 블록임을 명시하였다.
svg role에는 'img'를 제공하여 스크린 리더가 이를 식별할 수 있게 했다.

### login\_\_form

- user-id, user-passward, submit button을 포함한 속성을 작성했다. input-id와 user-id 중 네이밍을 고민하였는데, **무엇을** 이 태그가 받고 있는 지를 생각하여 user-id를 class로 지정했다.
- user-password의 최대값은 네이버에서 16자로 제한하고 있는데, 최근 보안이슈를 보고 구태여 지정하지 않았다.

또한, html 유효성 검사중

> The for attribute of the label element must refer to a non-hidden form control

에러가 발생하였는데, 이는 label과 input의 for, id 값을 맞춰주지 않아 발생한 에러였다.

## 결론과 회고

html 태그 하나하나 보고 복습하다보니 시간이 너무 걸려서 스타일링을 거의 못한 것이 너무 아쉽다..
일단 제출하고 수정을 거쳐야할 것 같다.
