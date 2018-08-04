# Setting up a new computer (change computers) for PlayBook HTML5 & WebWorks development

> Note:  
On Windows 10, it's possible to build an unsigned app but signing does not work because `bbwp` can't find the signing keys.

### Make a backup of the existing registered BlackBerry Code Signing Keys

    Files: author.p12, barsigner.csk, barsigner.db  
    Location (Windows 7): "C:\Users\<username>\AppData\Local\Research In Motion"


### Copy all three files (author.p12, barsigner.csk, barsigner.db) to the new computer in 
    "C:\Users\<username>\AppData\Local\Research In Motion" folder 
    // if needed create the "Research In Motion" folder

### Download and install the Adobe AIR SDK & Compiler (version 2.7)

    Search Google for "archived adobe air sdk"


### Download and instal the BlackBerry WebWorks SDK for PlayBook OS (tablet)

    http://developer.blackberry.com/playbook/html5/download/


### Verify and update %PATH% and %JAVA_HOME% Environment Variables

    "C:\<BlackBerry WebWorks SDK install folder>\jre\bin" has to be added to %PATH% and it needs to replace any
	previous path that was pointing to a different java bin

    %JAVA_HOME% is not required but if it is set for other programs (e.g. maven) then it has to be set to
	point to "C:\<BlackBerry WebWorks SDK install folder>\jre"

    <java></java> from bbwp.properties has to either be empty or "C:\<BlackBerry WebWorks SDK install folder>\jre"


### Verify debug token

    C:\<BlackBerry WebWorks SDK install folder>\bbwp\AirAppTemplates\src\blackberry-tablet.xml
	must contain proper <author> and <authorId> values 
    or <debug_token></debug_token> from bbwp.properties contains a full path to a valid debug token 

## Create a "Hello World!" PlayBook HTML5 & WebWorks app 

    (in a folder C:\Users\<username>\RippleSites\HelloWorld)
	
    /icon.png
    /index.html
    /config.xml


**new file** `index.html`

    <!DOCTYPE html>
    <html>
    <head>
        <title>HelloWorld</title>
        <meta id="viewport" name="viewport" content="user-scalable=no, width=device-width" />
    </head>
     
    <body>
        <div id="container">
            <h1>Hello World!</h1>
    
        </div>
    
    </body>
    </html>


**new file** `config.xml`
    
    <?xml version="1.0" encoding="UTF-8"?>
    
    <widget xmlns="http://www.w3.org/ns/widgets"
            xmlns:rim="http://www.blackberry.com/ns/widgets"
            version="1.0.0.0" id="HelloWorldApp">  
        <name>Hello World</name>
        <author>My name</author>
        <description>Hello World app</description>
        <icon src="icon.png"/>
        <content src="index.html"/>
    
    </widget>
