# things-msg-box-behavior

An element providing a starting point for your own reusable Polymer elements.


## Dependencies

Element dependencies are managed via [Bower](http://bower.io/). You can
install that via:

    npm install -g bower

Then, go ahead and download the element's dependencies:

    bower install


## Playing With Your Element

If you wish to work on your element in isolation, we recommend that you use
[Polyserve](https://github.com/PolymerLabs/polyserve) to keep your element's
bower dependencies in line. You can install it via:

    npm install -g polyserve

And you can run it via:

    polyserve

Once running, you can preview your element at
`http://localhost:8080/components/things-msg-box-behavior/`, where `things-msg-box-behavior` is the name of the directory containing it.


## Testing Your Element

Simply navigate to the `/test` directory of your element to run its tests. If
you are using Polyserve: `http://localhost:8080/components/things-msg-box-behavior/test/`

### web-component-tester

The tests are compatible with [web-component-tester](https://github.com/Polymer/web-component-tester).
Install it via:

    npm install -g web-component-tester

Then, you can run your tests on _all_ of your local browsers via:

    wct

#### WCT Tips

`wct -l chrome` will only run tests in chrome.

`wct -p` will keep the browsers alive after test runs (refresh to re-run).

`wct test/some-file.html` will test only the files you specify.


## Yeoman support

If you'd like to use Yeoman to scaffold your element that's possible. The official [`generator-polymer`](https://github.com/yeoman/generator-polymer) generator has a [`seed`](https://github.com/yeoman/generator-polymer#seed) subgenerator.


/**
 * 메시지 박스를 표시하는 Behavior
 * 메시지 박스는 크게 information, confirmation, prompt 형으로 구분된다.
 * information은 단순히 메시지를 표시하는 형식이고 confirmation은 사용자에게 확인을 받는 형식, 그리고 Prompt는 사용자에게 값을 받아오는 형식이다.
 * 각 메시지 박스 타입의 Function은 information - openInfoMsg, confirmation - openConfirmMsg, prompt - openPromptMsg로 구성된다.
 * confirmation과 prompt 타입은 사용자 응답이 'OK' 성일 경우 Callback 함수를 넘길 수 있다. (API 참조)
 * 각 Function은 config로 메시지 박스를 구성하는데 configuration 요소는 다음과 같다.
 *
 * config
 * 1) type : 메시지 박스의 아이콘 - info, success, warning, error, input, prompt (input과 prompt는 동일) 중 하나
 * 2) title : 메시지 박스의 타이틀
 * 3) text : 메시지 박스의 본문 메시지
 * 4) html : 메시지 박스의 본문을 Html 형식으로 구성할 지 여부, 기본값은 false이고 값이 true일 경우 text 값은 html로 구성되어야 한다.
 * 5) allowOutsideClick: 메시지 박스 창이 modal인 지 여부, 기본값은 false
 * 6) showConfirmButton: Confirm 버튼을 표시할 지 여부. 기본값은 true
 * 7) showCancelButton: Cancel 버튼을 표시할 지 여부, false
 * 8) closeOnConfirm: Confirm 버튼 클릭시 메시지 박스 창이 close될 지 여부, 기본값은 true
 * 9) closeOnCancel: Cancel 버튼을 클릭시 메시지 박스 창이 close될 지 여부, 기본값은 true
 * 10) confirmButtonText: Confirm 버튼의 텍스트 값, 기본값은 'OK'
 * 11) confirmButtonColor: Confirm 버튼의 색깔, 기본값은 '#8CD4F5'
 * 12) cancelButtonText: Cancel 버튼의 텍스트 값, 기본값은'Cancel'
 * 13) imageUrl: 삽입하고자 하는 이미지 URL, 기본값은 null
 * 14) imageSize: 삽입하고자 하는 이미지의 사이즈, 기본값은 null
 * 15) timer: 얼마 후에 자동으로 메시지 창이 close될 지 여부, (ex: 3초 후에 자동으로 닫혀야 한다면 3000, null이면 사용자 반응에 창이 닫힘), null,
 * 16) customClass: 커스터마이징 스타일을 구성할 경우 설정, 가본값은 ''
 * 17) animation: 창이 열리고 닫힐 때 애니메이션 효과 여부, 기본값은 true
 * 18) allowEscapeKey: esc키를 누를 때 창이 close될 지 여부, 기본값은 true
 * 19) inputType: type이 input이나 prompt일 경우 사용자에게 입력받을 Input 값의 타입, 기본값은 'text'
 * 20) inputPlaceholder: type이 input이나 prompt일 경우 사용자에게 입력받을 Input의 Placeholder, 기본값은 ''
 * 21) inputValue: type이 input이나 prompt일 경우 사용자에게 입력받은 Input 값
 * 22) showLoaderOnConfirm: 값이 true이면 Cancel과 Confirm 버튼을 비활성화한다. 기본값은 false
 *
 * @polymerBehavior Things.MsgBoxBehavior
 * @demo demo/index.html
 */
