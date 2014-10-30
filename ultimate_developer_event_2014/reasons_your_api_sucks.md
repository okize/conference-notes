## 12 reasons your api sucks

### Keith Casey

__Summary:__
Those first moments of using an API are pivotal. There’s nothing like downloading this week’s PDF of the documentation, setting up a SOAP client, reconfiguring all your URLs, and decoding the latest binary payloads. It makes your heart sing and your blood pressure rise. Just like there are code smells through the rest of your project, there are API smells that make them hard to design, hard to launch, and hard to maintain. We’ll use this time to explore a few common APIs to highlight those issues and demonstrate strategies to fix the issues before they become problems.

---

#### love at first bite

developers will set aside an hour to learn something but will likely be interrupted and will only get a few 10 minute chunks to review (but will remember spending an hour and not getting anywhere with your API)

should try to deliver an API experience that can deliver results in less than 10 minutes

### 1) Documentation

* consumable
* accurate & complete

* PDF - static (out of date), extra software, hard to search, may be hard to copy/paste
* HTML - always make documentation available as HTML

### 2) Incomplete/Wrong Documentation

* documentation tools
	* Swagger - http://swagger.io
	
* Helper documentation != API documentation

### 3) Getting started code

* examples - copy-paste-execute
* simplicity in code & interfaces

### 4) Too much boilerplate

### 5) SOAP as the interface

* REST is like borrowing $10 from a friend
* SOAP is like a mortgage

### 6) Illogical/Inconsistent

* consistent payloads
* nice when API routes are guessable
	* api/v1/users VS. api/v1/users/current

### 7) Poor workflow & modeling

affordances:

* what is the API producer's goal
* what problem(s)/task(s) does it make simple?
* what do you want to do?

### 8) Numerous approaches

* everyone is wrong & everyone is right simultaneously

### 9) Authentication

* don't roll your own authentication methods
* don't roll your own "encryption"

### 10) Your stuff is broken

* what does your uptime look like
* is the API deterministic? (output should be predictable)
* are the docs up to date?

### 11) Error messages

* make sure error messages are helpful & show user what steps to take to remedy issue
* can link to docs if sending error code

### 12) Logging & debugging

* https://www.runscope.com/

