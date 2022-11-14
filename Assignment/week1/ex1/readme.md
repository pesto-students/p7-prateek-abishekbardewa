# 1.What is the main functionality of the browser?

Answer: In simple terms the basic functionality is to access different website/services in a internet. Browser serves as a interface between user and world wide web.It gathers the information from web and displays to the user. The information is transferred using http(Hypertext Transfer Protocol) which defines how text, images and video are transmitted on the web.

# 2.High Level Components of a browser

Answer:

Click on the image link for [High Level Components of browser](../assets/browser-component.avif)

The user interface: It is comprises of different action that a user can perfom on a browser
that includes the address bar where user can type a address of a website , back/forward button, bookmarking menu, etc.

The browser engine: Gathers actions between the UI and the rendering engine.

The rendering engine: It is responsible for displaying requested content. It parses HTML and CSS, and displays the parsed content on the screen.

Networking: Responsible for making network calls such as HTTP requests

UI backend: This backend exposes a generic interface that is not platform specific. Underneath it uses operating system user interface methods.

JavaScript interpreter: Main functionality is to parse and execute JavaScript code.

Data storage: Mordern browser need to save all sorts of data locally, such as cookies, localStorage, IndexedDB, WebSQL and FileSystem which is achieved by data storage somponents of browser

# 3.Rendering engine and its use.

Answer: It is responsible for displaying requested content. It parses HTML and CSS, and displays the parsed content on the screen.
By default the rendering engine can display HTML and XML documents and images. It can display other types of data via extension; for example, displaying PDF documents using a PDF viewer plug-in.

# 4.Parsers (HTML, CSS, etc)

Answer:
Parsing means analyzing and converting a program into an internal format that a runtime environment can actually run.

In other words, parsing means taking the code we write as text (HTML, CSS) and transform it into something that the browser can work with. The parsing will be done by the browser engine.

The browser engine is a core component of every major browser and it's main role is to combine structure (HTML) and style (CSS) so it can draw the web page on our screens. It is also responsible to find out which pieces of code are interactive.

Three actively developed full browser engines:

Gecko
It was developed by Mozilla for Firefox. In the past it used to power several other browsers but at the moment, besides Firefox, Tor and Waterfox are the only ones still using Gecko. It is written in C++ and JavaScript, and since 2016, additionally in Rust.

WebKit
It's primarily developed by Apple for Safari. It also powers GNOME Web (Epiphany) and Otter. (surprinsingly enough, on iOS, all browsers including Firefox and Chrome, are also powered by WebKit). It it written in C++.

Blink, part of Chromium
Beginning as a fork of WebKit, it's primarily developed by Google for Chrome. It also powers Edge, Brave, Silk, Vivaldi, Opera, and most other browser projects (some via QtWebEngine). It is written in C++.

# 5. Script Processors

Answer:
The script processor executes Javascript code to process an event. The processor uses a pure Go implementation of ECMAScript 5.1 and has no external dependencies. This can be useful in situations where one of the other processors doesn’t provide the functionality to filter events.

# 6. Tree construction and # 8. Layout and Paint

Answer :
Click on the image link for [tree construction](../assets/tree-construction.avif)
The CSSOM and DOM trees are combined into a render tree, which is then used to compute the layout of each visible element and serves as an input to the paint process that renders the pixels to screen. Optimizing each of these steps is critical to achieving optimal rendering performance.

The DOM and CSSOM trees are combined to form the render tree.
Render tree contains only the nodes required to render the page.
Layout computes the exact position and size of each object.
The last step is paint, which takes in the final render tree and renders the pixels to the screen.

# 7 Order of script processing

Answer:
The Order of script processing goes through following steps:

1.Execution Stages
To configure the object attributes correctly so that the script elements behave as we expect
The following topics describe the execution stages :
Execution Stages
Activation
Generation
Processing
Completion

2.Time of Processing
The time at which the script is generated depends on the Generate Task at attribute that you define on the object Attributes page. You have two options:

Generate Task at: Activation time
The script is generated at the beginning of the generation stage.

Generate Task at: Runtime
The script is generated much later in the generation stage

Example
The following script uses a function to set the value of a variable to the current date and time:
:SET &CURRENTTIME# = SYS_TIME()

3.Order of Processing
Depending on the type of object, the task may have more than one Process page on which we can write scripts. The scripts in the Process pages are processed in the following order:
Pre-Process page and Process page
Child Post Process page
Post Process page

4.Processing In Scripts
The Automation Engine processes scripts line by line. The results of executed script elements (such as the value of a variable that has been set) are regularly written to the AE database. This process is referred to as a commit. Other scripts can only access these new or modified values after the values have been committed.
When scripts run for longer times, the Automation Engine automatically makes a commit every 5 seconds. In addition, some script elements that require processes to complete also result in commits.
