# NODE.JS

## An Introduction to Node.js

Source (article): [sitepoint - What is Node and When Should I Use It?](https://www.sitepoint.com/an-introduction-to-node-js/)

* **What is node.js?**
  * Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google's V8 JavaScript engine and libuv library.
* **In your own words, what is Chromes's V8 JavaScript Engine?**
  * Chrome's V8 engine is what Google Chrome and Chromium-based browsers run on. It is open-source, and compiles javascript into machine code. Node.js includes various upgrades to the engine, such as a file system API, HTTP library, and several OS-related utility methods.
* **What does it mean that node is a JavaScript runtime?**
  * Node can execute JavaScript on our computers, without the use of a browser.
* **What is npm?**
  * npm is the definitive JavaScript Package Manager bundled with Node.js. It includes over 1,000,000 packages available for download.
* **What version of node are you running on your machine?**
  * `node --version` > v14.17.4
* **What version of npm are you running on your machine?**
  * `npm --version` > 6.14.14
* **What command would you type to install a library/package called 'jshint'?**
  * `npm install -g jshunt` will install the jshint package globally.
* **What is node used for?**
  * Node is used for executing JavaScript on a machine. A further more common use is for executing JavaScript on a server. This functionality can be used to have a server perform certain tasks depending on input/output events.

## Pair Programming

Source (CF): [6 Reason for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)

* **What are the 6 reasons for pair programming?**
  1. **Greater efficiency** - two heads are better than one, and discussing problems as they're worked on can help solutions come about easier. Also when stuck, both programmers can do research at the same time.
  2. **Engaged collaboration** - working in pairs can keep both programmers engaged better. It can also keep both people from procrastinating or getting off track.
  3. **Learning from fellow students** - working with other people can expose devs to new concepts or approaches to problem solving that they may not have thought of themselves.
  4. **Social skills** - working in pairs can help develop better interpersonal skills, such as communication.
  5. **Job interview readiness** - pair programming is a common step in many interview processes. Practicing now can help prepare us for later.
  6. **Work environment readiness** - Upon hiring, many employers will use pair programming to get employees up to speed.
* **In your experience, which of these reasons have you found most beneficial?**
  * I would say learning from fellow students is pretty big for me. Talking through problems with peers often leads to interesting solutions.
* **How does pair programming work?**
  * One person acts as the "driver" and writes code, while the other works as the "navigator", researching directing code and looking things up as necessary.

## Things I want to know more about

So node.js makes sense right up until the part where a server actually fires off some JavaScript. Is that triggered by a fetch, or just a function? I guess that's the missing puzzle piece for me here.
