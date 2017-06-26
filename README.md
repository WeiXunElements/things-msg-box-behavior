# things-msg-box-behavior

The element that provides a starting point for your own reusable Polymer elements.


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
 * The behavior that displays a message box.
 * The message boxes are largely classified into information, confirmation and prompt types.
 * Information is simply a format for displaying messages, and confirmation is a format for receiving confirmation from the user, and Prompt is a format for receiving values ​​from the user.
 * The function of each message box type consists of information - openInfoMsg, confirmation - openConfirmMsg, and prompt - openPromptMsg.
 * The confirmation and prompt types can pass a Callback function if the user response is 'OK'. (API reference)
 * Each function configures a message box with config, and the configuration elements are as below.
 *
 * config
 * 1) type: One of the message box icons - info, success, warning, error, input, prompt (input and prompt are the same)
 * 2) title: The title of the message box
 * 3) text: The body message of the message box
 * 4) html: It means whether to configure the body of the message box in HTML format. The default value is false. If the value is true, the text value should be composed of HTML.
 * 5) allowOutsideClick: It means whether the message box window is modal. The default value is false.
 * 6) showConfirmButton: It means whether to display the Confirm button. The default value is true.
 * 7) showCancelButton: It means whether to display the Cancel button. The default value is false.
 * 8) closeOnConfirm: It means whether to close the message box window when the Confirm button is clicked. The default value is true.
 * 9) closeOnCancel: It means whether to close the message box window when the Cancel button is clicked. The default value is true.
 * 10) confirmButtonText: The text value of the Confirm button. The default value is 'OK'.
 * 11) confirmButtonColor: The color of the Confirm button. The default value is '#8CD4F5'.
 * 12) cancelButtonText: The text value of the Cancel button. The default value is 'Cancel'.
 * 13) imageUrl: The image URL you want to insert. The default value is null.
 * 14) imageSize: The size of the image you want to insert. The default value is null.
 * 15) timer: It means whether the message window will be closed automatically after some time. (ex: 3000 if it should be closed automatically after 3 seconds, and null if it should be closed after user response). The default value is null.
 * 16) customClass: Set when configure the customizing styles. The default value is ''.
 * 17) animation: It means whether the animation is animated when the window is opened and closed. The default value is true.
 * 18) allowEscapeKey: It means whether the window is closed when the esc key is typed. The default value is true.
 * 19) inputType: The type of the Input value which will be entered by the user when the type is input or prompt. The default value is 'text'.
 * 20) inputPlaceholder: The Placeholder of the Input which will be entered by the user when the type is input or prompt. The default value is ''.
 * 21) inputValue: The Input value which will be entered by the user when the type is input or prompt.
 * 22) showLoaderOnConfirm: If the value is true, disable the Cancel and Confirm buttons. The default value is false.
 *
 * @polymerBehavior Things.MsgBoxBehavior
 * @demo demo/index.html
 */
