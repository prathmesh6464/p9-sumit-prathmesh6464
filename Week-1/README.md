Exercise1.1:

Digaram :

					  UI Backend
					       /\
						   ||
						   \/						
  User Interface <--> Browser Engine <--> Rendering engine <--> Networking (HTTP request to server) 
					       /\							   <--> JavaScript Interpreter
						   ||                              
					       \/
					Data Persistence layer
	                                               									
	


The main functionality of the browser :
By using web browser, anyone can access webpage for getting information and web browser works on client - server model.

High Level Components of a browser is as follows :
1.	User interface   		: all view of browser address bar, title bar, screen etc.
2.	Browser engine    		: Interface Between User Interface and Rendering Engine also Commnucate with UI Backend and Data 
								persistence layer
3.	Rendering engine  		: it Commnucate with Networking layer and JavaScript Interpreter 
4.	Networking      	  	: Uses HTTP Request and fetch required server with Ip Address 
5. 	UI backend  	      	: Used to draw combo boxes and windows.
6. 	JavaScript interpreter	: Used to interprete java script
7.  Data persistence layer	: Used to store and receive cache, cookies etc.

For fetching web site on browser need to do following steps :
step 1 - After writing URL on address bar click on Enter button
step 2 - For searching ip address request goes from browser to DNS or first it searches in Cache, cookies.
			(Data persistence layer stores data localy, In Data persistencelayer, Browser engine stores cache, cookies etc. to Data 
			persistence layer)
step 3 - DNS gives ip address to browser engine 
step 4 - Browser engine sends request to rendering engine 
step 5 - Redering engine sends to Networking layer, rendering engine sends Request to ip address which was received by DNS Server
step 6 - IP address matches with Expected server, server send reponse to rendering engine.	     		
step 7 - Rendering engine forms the DOM Structure of HTML and CSS, this DOM is in format of Tree structure.
step 8 - DOM element is used by JavaScript. JavaScript code is paresed by javascript interpreter.
step 9 - After parsing html css data by rendering engine, it displays data to user interface, Browser engine is interface 
		 between rendering engine and User Interface.
step 10- If We click button on Web browser then process to hit target is as follow :
		 		 
		 Diagram :

								  --------------->    Capture Phase     ----------->
			Window of Web page (button clicked) -> Document -> HTML -> BODY -> button (Target Phase)
								  <---------------    Bubbling Phase    <----------- 
