# analyze-DrawSVGPlugin
analyze DrawSVGPlugin of greensock

```js
function w() {
  return String.fromCharCode.apply(null, arguments)
}
const u = w(103, 114, 101, 101, 110, 115, 111, 99, 107, 46, 99, 111, 109)   // "greensock.com"
const $$0 = w(102, 105, 108, 101, 58, 47, 47)                               // "file://"
const $$1 = w(108, 111, 99, 97, 108, 104, 111, 115, 116)                    // "localhost"
const $$2 = w(49, 50, 55, 46, 48, 32, 48, 46, 49)                           // "127.0 0.1"

// 我认为这里是作者写的一个 bug
// 本地回环地址 127.0.0.1 的 ascii 码应该为 [49, 50, 55, 46, 48, 46, 48, 46, 49]
// 作者这里写的 ascii 码为                 [49, 50, 55, 46, 48, 32, 48, 46, 49]
// 其中第五项为 32, 转议为字符串为 " " （一个空格），所以作者写的地址转议后是 “127.0 0.1”
// 如果要想得到 “127.0.0.1”, 只需要将 32 改为 46 即可

const f = "DrawSVGPlugin",
  c = function (e) {
    for (
      var t = 0 === (window ? window.location.href : "").indexOf($$0) || -1 !== e.indexOf($$1) || -1 !== e.indexOf($$2),
      n = [
        u, // "greensock.com"
        w(99, 111, 100, 101, 112, 101, 110, 46, 105, 111),
        // "codepen.io",
        w(99, 111, 100, 101, 112, 101, 110, 46, 112, 108, 117, 109, 98, 105, 110, 103),
        // "codepen.plumbing",
        w(99, 111, 100, 101, 112, 101, 110, 46, 100, 101, 118),
        // "codepen.dev",
        w(99, 111, 100, 101, 112, 101, 110, 46, 97, 112, 112),
        // "codepen.app",
        w(112, 101, 110, 115, 46, 99, 108, 111, 117, 100),
        // "pens.cloud",
        w(99, 115, 115, 45, 116, 114, 105, 99, 107, 115, 46, 99, 111, 109),
        // "css-tricks.com",
        w(99, 100, 112, 110, 46, 105, 111),
        // "cdpn.io",
        w(112, 101, 110, 115, 46, 105, 111),
        // "pens.io",
        w(103, 97, 110, 110, 111, 110, 46, 116, 118),
        // "gannon.tv",
        w(99, 111, 100, 101, 99, 97, 110, 121, 111, 110, 46, 110, 101, 116),
        // "codecanyon.net",
        w(116, 104, 101, 109, 101, 102, 111, 114, 101, 115, 116, 46, 110, 101, 116),
        // "themeforest.net",
        w(99, 101, 114, 101, 98, 114, 97, 120, 46, 99, 111, 46, 117, 107),
        // "cerebrax.co.uk",
        w(116, 121, 109, 112, 97, 110, 117, 115, 46, 110, 101, 116),
        // "tympanus.net",
        w(116, 119, 101, 101, 110, 109, 97, 120, 46, 99, 111, 109),
        // "tweenmax.com",
        w(116, 119, 101, 101, 110, 108, 105, 116, 101, 46, 99, 111, 109),
        // "tweenlite.com",
        w(112, 108, 110, 107, 114, 46, 99, 111),
        // "plnkr.co",
        w(104, 111, 116, 106, 97, 114, 46, 99, 111, 109),
        // "hotjar.com",
        w(119, 101, 98, 112, 97, 99, 107, 98, 105, 110, 46, 99, 111, 109),
        // "webpackbin.com",
        w(97, 114, 99, 104, 105, 118, 101, 46, 111, 114, 103),
        // "archive.org",
        w(99, 111, 100, 101, 115, 97, 110, 100, 98, 111, 120, 46, 105, 111),
        // "codesandbox.io",
        w(99, 115, 98, 46, 97, 112, 112),
        // "csb.app",
        w(115, 116, 97, 99, 107, 98, 108, 105, 116, 122, 46, 99, 111, 109),
        // "stackblitz.com",
        w(99, 111, 100, 105, 101, 114, 46, 105, 111),
        // "codier.io",
        w(109, 111, 116, 105, 111, 110, 116, 114, 105, 99, 107, 115, 46, 99, 111, 109),
        // "motiontricks.com",
        w(115, 116, 97, 99, 107, 111, 118, 101, 114, 102, 108, 111, 119, 46, 99, 111, 109),
        // "stackoverflow.com",
        w(115, 116, 97, 99, 107, 101, 120, 99, 104, 97, 110, 103, 101, 46, 99, 111, 109),
        // "stackexchange.com",
        w(106, 115, 102, 105, 100, 100, 108, 101, 46, 110, 101, 116)
        // "jsfiddle.net",
      ], r = n.length; - 1 < --r;) if (- 1 !== e.indexOf(n[r])) return !0;
    return t && window && window.console && console.log(
      w(87, 65, 82, 78, 73, 78, 71, 58, 32, 97, 32, 115, 112, 101, 99, 105, 97, 108, 32, 118, 101, 114, 115, 105, 111, 110, 32, 111, 102, 32)
      + f +
      w(32, 105, 115, 32, 114, 117, 110, 110, 105, 110, 103, 32, 108, 111, 99, 97, 108, 108, 121, 44, 32, 98, 117, 116, 32, 105, 116, 32, 119, 105, 108, 108, 32, 110, 111, 116, 32, 119, 111, 114, 107, 32, 111, 110, 32, 97, 32, 108, 105, 118, 101, 32, 100, 111, 109, 97, 105, 110, 32, 98, 101, 99, 97, 117, 115, 101, 32, 105, 116, 32, 105, 115, 32, 97, 32, 109, 101, 109, 98, 101, 114, 115, 104, 105, 112, 32, 98, 101, 110, 101, 102, 105, 116, 32, 111, 102, 32, 67, 108, 117, 98, 32, 71, 114, 101, 101, 110, 83, 111, 99, 107, 46, 32, 80, 108, 101, 97, 115, 101, 32, 115, 105, 103, 110, 32, 117, 112, 32, 97, 116, 32, 104, 116, 116, 112, 58, 47, 47, 103, 114, 101, 101, 110, 115, 111, 99, 107, 46, 99, 111, 109, 47, 99, 108, 117, 98, 47, 32, 97, 110, 100, 32, 116, 104, 101, 110, 32, 100, 111, 119, 110, 108, 111, 97, 100, 32, 116, 104, 101, 32, 39, 114, 101, 97, 108, 39, 32, 118, 101, 114, 115, 105, 111, 110, 32, 102, 114, 111, 109, 32, 121, 111, 117, 114, 32, 71, 114, 101, 101, 110, 83, 111, 99, 107, 32, 97, 99, 99, 111, 117, 110, 116, 32, 119, 104, 105, 99, 104, 32, 104, 97, 115, 32, 110, 111, 32, 115, 117, 99, 104, 32, 108, 105, 109, 105, 116, 97, 116, 105, 111, 110, 115, 46, 32, 84, 104, 101, 32, 102, 105, 108, 101, 32, 121, 111, 117, 39, 114, 101, 32, 117, 115, 105, 110, 103, 32, 119, 97, 115, 32, 108, 105, 107, 101, 108, 121, 32, 100, 111, 119, 110, 108, 111, 97, 100, 101, 100, 32, 102, 114, 111, 109, 32, 101, 108, 115, 101, 119, 104, 101, 114, 101, 32, 111, 110, 32, 116, 104, 101, 32, 119, 101, 98, 32, 97, 110, 100, 32, 105, 115, 32, 114, 101, 115, 116, 114, 105, 99, 116, 101, 100, 32, 116, 111, 32, 108, 111, 99, 97, 108, 32, 117, 115, 101, 32, 111, 114, 32, 111, 110, 32, 115, 105, 116, 101, 115, 32, 108, 105, 107, 101, 32, 99, 111, 100, 101, 112, 101, 110, 46, 105, 111, 46)
    ),
      /**
       * WARNING: a special version of DrawSVGPlugin
       * is running locally, but it will not work on a live domain because it is a membership benefit of Club GreenSock. Please sign up at http://greensock.com/club/ and then download the 'real' version from your GreenSock account which has no such limitations. The file you're using was likely downloaded from elsewhere on the web and is restricted to local use or on sites like codepen.io.
       */
      t || !(window.location.href = "https://"
        + u                                                                                                      // "greensock.com"
        + w(47, 114, 101, 113, 117, 105, 114, 101, 115, 45, 109, 101, 109, 98, 101, 114, 115, 104, 105, 112, 47) // "/requires-membership/"
        + "?plugin=" + f + "&source=codepen")
  }(window ? window.location.host : "")
```
