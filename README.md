# InternetBS Reseller API PHP Class
PHP class to get easy and quick access to all InternetBS reseller API functions

### Supported Features
--------
* Domain related operations
* Managing Private (Anonymous) WHOIS Service
* DNS management related operations
* Managing Email Forwarding
* Managing Url Forwarding
* Nameservers (host) related operations
* Account related operations
* Write log operations and customize logging method
* Customize error handling


### Usage Example - Quick Start
--------
Usage of Internet BS Reseller API class is very easy. Just see the example below:
```php
include_once('InternetBS.php');

try {

    // You already can execute command at test server! Let's do:
    if(InternetBS::api()->domainCheck('check-at-test-server.com'))    {
        echo "Domain available!\n";
    } else {
        echo "Domain unavailable!\n";
    }

    // To execute command at live server you just need to set your API key and password.
    // Do it just once and after that all commands will be executed at live server.
    InternetBS::init('MyApiKey', 'mypassword');

    // Now you may execute command at live server
    if(InternetBS::api()->domainCheck('check-at-live-server.org'))    {
        echo "Domain available!\n";
    } else {
        echo "Domain unavailable!\n";
    }

    // Next API command will be also executed at live server
    // For example we may get current registrar prices
    print_r(InternetBS::api()->accountPriceListGet('USD'));

 } catch (Exception $e) {
     echo "OOPS Error: ".$e->getMessage()."\n";
 }
```

Looks simple, isn't it? See other examples in "example" folder. Also, you can find a class documentation generated by phpDocumentor in "doc" folder.


### How to Test Code at Sandbox Server
--------
If you don't specify a valid API key and password, then all commands will be executed at test server. So to execute command on test server, you actually no need to do anything, it will be done by default.

**NOTE:** API test server much slower than the real api server. If some commands work slow at test server do not worry about that too much, most probably at live server it will be executed much faster.

### How To Get Real API Key?
--------
To execute commands at live server you need valid API key. To get an API key just performs 3 simple steps:

 1. Click  [here to create new account](https://internetbs.net/newaccount.html?pId=apiclass) at InternetBS site.
 2. Open control panel and find at the top of the page (right upper conner) link "**Get API Key**", click that link.
 3. Add funds to your balance in order to be able to execute payable operations like domain registration, renew, transfer and so on.

When you are done you will get your own API key and password. Now you can execute any commands at real live server. Don't forget to set your API/password once somewhere at script begin (before first command execution) like:
```php
InternetBS::init('PUT-YOUR-API-HERE', 'PASSWORD');
//.... after that we can execute any command(s) at live server
```

### Useful Links
--------
* [Ready to use plugins for leading web hosting and billing platforms] (http://internetbs.net/en/domain-name-registrations/domain-automation-plugins-modules.html?pId=apiclass)
* [Reseller/Registrar Domain Name API Documentation] (http://internetbs.net/ResellerRegistrarDomainNameAPI/)

