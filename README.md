## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
Protocol, domain, port, path, query, anchor.

Protocol: HTTP is a set of rules for transferring files incl. text, images, sound, video etc. on the www. It runs on top of TCP/IP.

Domain: a group of computers on a network accessed and administered under the same protocol/set of rules. 

Port: the endpoint of communication, i.e. the data that has been send via the internet.

Path: the path to the content that is displayed in the browser.

Query: data that doesn't fit into the path structure, often includes info from html forms.

Anchor: points to a specific place on a page.
```

* Name the pieces of the following urls:
	* `https://www.google.com/`

  ```
  https => protocol
  www.google.com => domain
  ```

	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`

  ```
  https => protocol
  workbook.galvanize.com => domain
  /cohorts/41/learning_experiences/367 => path
  ```

	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`

  ```
  http => protocol
  locahost => domain
  5000 => port
  /animals/puppies => path
  onlycute=1&size=medium => query
  firstpuppy => anchor
  ```

	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`

  ```
  https => protocol
  en.wikipedia.org => domain
  /wiki/List_of_HTTP_status_codes => path
  4xx_Client_Error => anchor

  ```

* Can a server use more than 1 port?

```
Yes.
```

* Why is https different than http?

```
https is more secure. It sends information securely between computers based on a certain "code" the computers aggree on to use between them.
```

* How does a server interpret the following url's query paramter. What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie

It creates an array of strings with puppy names.
```

__HTTP Request/Response__

* Name at least 4 http verbs

```
GET, POST, PUT, DELETE.
```

* What is each verb useful for in your own words

```
GET creates a data request to the server - "asking the server for information, e.g. a website".

POST sends data to a server.

PUT updates already existing data on the server.

DELETE deletes information on the server. 
```

* What does idempotent mean?

```
An operation that gives the same result no matter how many times it is done, e.g. GET requests made many times in a row, but doesn't change the server status.
```

* Name the 5 http status code ranges.  What are they used for in general?

```
1xx
2xx
3xx
4xx
5xx

Status codes is a way for the server to communicate with the client, i.e. a response to a GET request from the client.
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
The browser redirects the client to another domain, as the current domain has been permanently removed.
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
	* Content-type
	* User-agent
	* Set-cookies
	* Cache-control
	* Cookie

```
  * Accept => requests
  * Content-type => both
  * User-agent => requests
  * Set-cookies => response
  * Cache-control => request
  * Cookie => request
```

* Is the following a http request or response?  How do you know for each?

```
First one is a response, because it includes a status code from the server: 200 OK.

The second one is a request, because it includes the header Accept, meaning that the client is specifying what type of data it is expecting to get back from the server. 
```

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

__JSON__

* Describe what JSON is.  What is it used for.

```
JSON is a data format used for client/server communication. 
```

* Convert the following map into a javascript object then console log the age.

```
var githubObj = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}')

console.log(githubObj.age);
});
```

* Convert the following to a javascript object.  Console log each company name.

```
var companyObj = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}')

companyObj.Companies.map(function(compName) { 
  console.log(compName.company);
});

```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};

var jsonObj = JSON.stringify(myObj);
console.log(jsonObj);

```

__MISC__

* Describe what DNS is.

```
A system that translates domain names to IP addresses, which identifies computers connected to the internet.
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
-v means to be more verbose or talkative, i.e. seeing what's going on under the hood during an operation/shows hidden operations.

-X means requesting something from the server, e.g. GET.
```

* What is TCP/IP?  How does it interact with HTTP?

```
The basic communication language/protocol of the internet. It manages the assembling of a message or file into smaller packets, which are send over the internet and reassembled to the original message when arriving at the right port. TCP/IP is the underlying application to the web. HTTP use TCP/IP to get to the internet.

```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
No, the TCP/IP protocol is responsible for that. 
```

