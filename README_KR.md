# things-msg-box-behavior

이는 사용자 자신만의 재사용 가능한 polymer element의 시작점을 제공하는 element이다.


## Dependencies

element의 종속성은 [Bower](http://bower.io/)를 통해 관리되며, 아래의 방법을 통해 설치할 수 있다.

    npm install -g bower

다음, element의 종속성을 다운로드한다.

    bower install


## Playing With Your Element

element를 독립적으로 처리하려면 [Polyserve](https://github.com/PolymerLabs/polyserve)를 사용하여 element의 bower 의존성을 유지하도록 하며, 이는 아래의 방법을 통해 설치할 수 있다.

    npm install -g polyserve

그리고, 아래의 방법을 통해 실행할 수 있다.

    polyserve

element를 실행한 경우, `things-msg-box-behavior`가 디렉토리 이름으로 포함되어 있는 `http://localhost:8080/components/things-msg-box-behavior/`를 통해 이를 미리 확인할 수 있다. 


## Testing Your Element

element의 `/test` 디렉토리로 이동하여 테스트를 실행한다. polyserve를 사용할 경우: `http://localhost:8080/components/things-msg-box-behavior/test/`

### web-component-tester

이 테스트는 [web-component-tester](https://github.com/Polymer/web-component-tester)와 호환되며, 아래와 같이 설치한다.

    npm install -g web-component-tester

다음, 아래와 같이 _모든_ 로컬 브라우저에서 테스트를 실행할 수 있다.

    wct

#### WCT Tips

`wct -l chrome`은 크롬에서만 테스트를 실행한다.

`wct -p`는 테스트가 실행된 후 브라우저를 계속 활성화(새로고침을 통해 다시 실행)한다.

`wct test/some-file.html`은 지정한 파일들만 테스트한다.


## Yeoman support

Yeoman을 사용하여 element를 설치하는 방법도 가능하다. 공식적인 [`generator-polymer`](https://github.com/yeoman/generator-polymer) 생성기에 [`seed`](https://github.com/yeoman/generator-polymer#seed)라는 하위 생성기가 있기 때문이다.


/**
 * 메시지 박스를 표시하는 Behavior.
 * 메시지 박스는 크게 information, confirmation, prompt 형으로 구분된다.
 * Information은 단순히 메시지를 표시하는 형식, Confirmation은 사용자에게 확인을 받는 형식, Prompt는 사용자에게 값을 받아오는 형식이다.
 * 각 메시지 박스 타입의 Function은 information - openInfoMsg, confirmation - openConfirmMsg, prompt - openPromptMsg로 구성된다.
 * confirmation과 prompt 타입은 사용자 응답이 'OK'일 경우 콜백 함수를 전달할 수 있다. (API 참조)
 * 각 Function은 config로 메시지 박스를 구성하며, configuration 요소는 다음과 같다.
 *
 * config
 * 1) type: 메시지 박스의 아이콘 - info, success, warning, error, input, prompt (input과 prompt는 동일) 중 하나.
 * 2) title: 메시지 박스의 타이틀.
 * 3) text: 메시지 박스의 본문 메시지.
 * 4) html: 메시지 박스의 본문을 HTML 형식으로 구성할 지 여부. 기본값은 false이고, 값이 true일 경우 text 값은 html로 구성되어야 한다.
 * 5) allowOutsideClick: 메시지 박스 창이 modal인 지 여부. 기본값은 false.
 * 6) showConfirmButton: Confirm 버튼을 표시할 지 여부. 기본값은 true.
 * 7) showCancelButton: Cancel 버튼을 표시할 지 여부. 기본값은 false.
 * 8) closeOnConfirm: Confirm 버튼 클릭시 메시지 박스 창이 close될 지 여부. 기본값은 true.
 * 9) closeOnCancel: Cancel 버튼을 클릭시 메시지 박스 창이 close될 지 여부. 기본값은 true.
 * 10) confirmButtonText: Confirm 버튼의 텍스트 값. 기본값은 'OK'.
 * 11) confirmButtonColor: Confirm 버튼의 색깔. 기본값은 '#8CD4F5'.
 * 12) cancelButtonText: Cancel 버튼의 텍스트 값. 기본값은 'Cancel'.
 * 13) imageUrl: 삽입하고자 하는 이미지 URL. 기본값은 null.
 * 14) imageSize: 삽입하고자 하는 이미지의 사이즈. 기본값은 null.
 * 15) timer: 얼마 후에 자동으로 메시지 창이 close될 지 여부. (ex: 3초 후에 자동으로 닫혀야 한다면 3000, null이면 사용자 반응에 창이 닫힘). 기본값은 null.
 * 16) customClass: 커스터마이징 스타일을 구성할 경우 설정. 기본값은 ''.
 * 17) animation: 창이 열리고 닫힐 때 애니메이션 효과 여부. 기본값은 true.
 * 18) allowEscapeKey: esc키를 누를 때 창이 close될 지 여부. 기본값은 true.
 * 19) inputType: type이 input이나 prompt일 경우 사용자에게 입력받을 Input 값의 타입. 기본값은 'text'.
 * 20) inputPlaceholder: type이 input이나 prompt일 경우 사용자에게 입력받을 Input의 Placeholder. 기본값은 ''.
 * 21) inputValue: type이 input이나 prompt일 경우 사용자에게 입력받은 Input 값.
 * 22) showLoaderOnConfirm: 값이 true이면 Cancel과 Confirm 버튼을 비활성화한다. 기본값은 false.
 *
 * @polymerBehavior Things.MsgBoxBehavior
 * @demo demo/index.html
 */
