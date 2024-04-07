# waht is the main functionality of browser?

browser is mainly used for rendering web sites, browser works on client server model, by using browser we send request to server for particular web page, when server responsed to browser's sent request then we able to see web page on browser

# High Level Components of a browser

![high level component of browser](./Images/how%20browser%20works.png "components in browser")

- User Interface: The user interface is the space where users interact with the browser. It encompasses elements such as bookmarks, an address bar for entering website URLs, back and forward buttons for navigation, tabs for multitasking, and menus for accessing various browser features and settings. The user interface provides a visually intuitive way for users to control and navigate the browser.

- Browser Engine: The browser engine acts as the core of the browser, handling user interactions, rendering web pages, and facilitating communication with other components. It coordinates the flow of information between the user interface, rendering engine, and other browser components. The browser engine ensures that user actions, such as clicking a link or entering a URL, are properly processed and trigger the appropriate actions within the browser.

- Rendering Engine: The rendering engine is responsible for displaying the content of web pages within the browser. It takes the HTML, CSS, and JavaScript code of a web page and converts it into a visual display that users can see. The rendering engine interprets the HTML structure, applies the CSS styles to determine the page’s layout and appearance, and executes any JavaScript code to add interactivity and dynamic elements to the web page.

- JavaScript Interpreter: The JavaScript interpreter is a component within the browser that executes JavaScript code found on web pages. JavaScript is a programming language commonly used for adding interactivity and dynamic functionality to websites. The interpreter ensures that JavaScript code is properly executed, allowing web pages to respond to user actions, update content dynamically, and interact with APIs and other web technologies.

- Networking: The networking component of a browser handles various aspects of network communication. It is responsible for resolving website URLs (using DNS) into IP addresses, sending HTTP requests to web servers, establishing network connections, and receiving and processing the responses. The networking component plays a crucial role in fetching web page resources, such as HTML, CSS, images, and other files, from servers and delivering them to the rendering engine for display.

- Data storage: This is a persistence layer. The browser may need to save all sorts of data locally, such as cookies. Browsers also support storage mechanisms such as localStorage, session storage.

It is important to note that browsers such as Chrome run multiple instances of the rendering engine: one for each tab. Each tab runs in a separate process.

# Rendering engine and its use

![flow of rendering engine](./Images/mainflow.png "fig : flow of rendering tree")

The responsibility of the rendering engine is display of the requested contents on the browser screen. The rendering engine will start getting the contents of the requested document from the networking layer.
The rendering engine will start parsing the HTML document and convert elements to DOM nodes in a tree called the "content tree". The engine will parse the style data, both in external CSS files and in style elements. Styling information together with visual instructions in the HTML will be used to create another tree: the render tree.

The render tree contains rectangles with visual attributes like color and dimensions. The rectangles are in the right order to be displayed on the screen.

After the construction of the render tree it goes through a "layout" process. This means giving each node the exact coordinates where it should appear on the screen. The next stage is painting - the render tree will be traversed and each node will be painted using the UI backend layer.

# Parsers (HTML, CSS)

Parsing a document means translating it to a structure the code can use. The result of parsing is usually a tree of nodes that represent the structure of the document. This is called a parse tree or a syntax tree.

Parsing can be separated into two sub processes: lexical analysis and syntax analysis.

Lexical analysis is the process of breaking the input into tokens. Tokens are the language vocabulary: the collection of valid building blocks. In human language it will consist of all the words that appear in the dictionary for that language.

Syntax analysis is the applying of the language syntax rules.

Parsers usually divide the work between two components: the lexer (sometimes called tokenizer) that is responsible for breaking the input into valid tokens, and the parser that is responsible for constructing the parse tree by analyzing the document structure according to the language syntax rules.

The parsing process is iterative. The parser will usually ask the lexer for a new token and try to match the token with one of the syntax rules. If a rule is matched, a node corresponding to the token will be added to the parse tree and the parser will ask for another token.

If no rule matches, the parser will store the token internally, and keep asking for tokens until a rule matching all the internally stored tokens is found. If no rule is found then the parser will raise an exception. This means the document was not valid and contained syntax errors.

**_HTML document parsing_**

> Fetched HTML ----> convert to Raw Bytes (0 or 1 format) ----> Covert to Character (`<p>hello <span> bro </sapn> how are you <p>`)----> Parsed to token ([HTML],[Body],[H1],[P]) ----> Convert to Object {tag:H1,...} ----> create relationship between created Objects (parent child) ----> Nodes ----> DOM tree created

!["flow of creating dom tree"](./Images/flow%20of%20creating%20dom%20tree.png "flow of creating dom tree")

### HTML After Parsing

![HTML tree after parsed](./Images/htmlelementtree.png "fig : HTML tree after parsed")

**_CSS document parsing_**

> Fetched CSS ----> convert to Raw Bytes (0 or 1 format) ----> Covert to Character ----> Parsed to token ----> Convert to Object ----> create relationship between created Objects (parent child)-----> Nodes ----> CSS-OM tree created

### CSS After Parsing

![CSS tree after parsed](./Images/cssparsedtree.png "fig : CSS tree after parsed")

# Tree construction

> DOM tree + CSS-OM = Render Tree (in redering engine)

![The render tree and the corresponding DOM treen](./Images/attachment.png "fig : The render tree and the corresponding DOM tree")

# Script Processors

JavaScript interpreter is a component within the browser that executes JavaScript code found on web pages. JavaScript is a programming language commonly used for adding interactivity and dynamic functionality to websites. The interpreter ensures that JavaScript code is properly executed, allowing web pages to respond to user actions, update content dynamically, and interact with APIs and other web technologies.

# Order of script processing

The model of the web is synchronous. Authors expect scripts to be parsed and executed immediately when the parser reaches a `<script>` tag. The parsing of the document halts until the script has been executed. If the script is external then the resource must first be fetched from the network, this is also done synchronously, and parsing halts until the resource is fetched. This was the model for many years and is also specified in HTML4 and 5 specifications. Authors can add the "defer" attribute to a script, in which case it won't halt document parsing and will execute after the document is parsed. HTML5 adds an option to mark the script as asynchronous so it will be parsed and executed by a different thread.

### script processing in case of DOM and CSS-OM

- while DOM is being created or processed, found `<script>` tag then DOM process is stopped and javascript execution starts, after finishing javascript execution then again DOM continues its process.
- but in case of CSS-OM is being processed or created, found Javascript code then, javascript execution have to halted it's execution till CSS-OM process gets complete.

![DOM and CSS-OM Cases](./Images/javascript%20execution%20cases.png "DOM and CSS-OM Cases")

# Layout and Painting

- Using the render tree, the browser calculates the exact position and size of each element on the page. This involves considering factors like margins, padding, and element nesting. This stage determines the overall layout of the content.
- the render tree goes through the layout process. When a render tree is created, the position or size values are not assigned. The entire process of calculating values for evaluating the desired position is called a layout process. In this process, every node is assigned the exact coordinates. This ensures that every node appears at an accurate position on the screen. (layout happens in rendering engine)
- After the construction of the render tree it goes through a "layout" process. This means giving each node the exact coordinates where it should appear on the screen. The next stage is painting - the render tree will be traversed and each node will be painted using the UI backend layer.
- the render tree is traversed, and the renderer’s paint() method is invoked, which paints each node on the screen using the UI backend layer. (painting happens in UI Backend)
