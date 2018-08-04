# Deploy to a device

## Before you begin

* make sure that your BlackBerry PlayBook tablet is on the same network as your computer
* make sure that your BlackBerry PlayBook tablet is in ***Development Mode***
* at a command prompt, navigate to `blackberry-tablet-sdk\bin` in your BlackBerry PlayBook OS SDK folder

## Create a debug token

// type the following command   
`blackberry-debugtokenrequest -storepass <KeystorePassword> -devicepin <device PIN> <debug_token_file_name.bar>`

// example <br />
`blackberry-debugtokenrequest -storepass <KeystorePassword> -devicepin <device PIN> "C:\BlackBerryApps\DebugToken.bar"`

## Verify a debug token

// type the following command   
`blackberry-debugtokenrequest -verify "C:\BlackBerryApps\DebugToken.bar"`

## Install a debug token

// type the following command   
`blackberry-deploy -installDebugToken <path to debug token> -device <Development Address> -password <device password>`

// example <br />
`blackberry-deploy -installDebugToken "C:\BlackBerryApps\DebugToken.bar" -device 192.168.0.108 -password 123456`

## Install and launch an application

// run the following command  
`blackberry-deploy -installApp -launchApp -package "C:\BlackBerryApps\HelloWorld.bar" -device 192.168.0.1 -password 123456`
