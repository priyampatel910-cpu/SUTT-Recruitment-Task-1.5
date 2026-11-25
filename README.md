# SUTT Task 1.5

## Task

I have already coded a polls app previously, so with your permission, I am pasting the GitHub repo link instead of creating a clone project.

[GitHub repo](https://github.com/priyampatel910-cpu/DVM-Backend)

The usage instructions are pretty simple:
1. Clone the repo:
	```
	git clone https://github.com/priyampatel910-cpu/DVM-Backend
	```
2. Go to the project root. From there, run:
   
    Run these bash commands in order.
	```
 	cd DVM-Backend/tasks
	python manage.py runserver
	```

4. Open a browser and visit [127.0.0.1:8000](http://127.0.0.1:8000)

## Q&A

### Q1.
 A request is generated based on the parameters entered in the URL (example, request method, protocol scheme, domain name, etc.)
 
 This request is first sent by the browser to the WSGI, for if present, to a reverse proxy which diverts the request to a specified server's WSGI. WSGI converts the plain HTTP request into a python function which is processed by Django. Django fetches data and renders templates and hand it back to WSGI, which converts the response back to HTTP format and passes the templates to the browser or the reverse proxy (which in turn passes it to the browser)

### Q2.
 Client, basically is the user accessing your website through the internet, typing your website's URL. 
 
 Server is a computing system which has all the Django files like view and models, and databases with the data.
 
 When a client interacts with the templates in your website, they send requests to the server. The defined logic in Django understands the request, and passes suitable data back to the client in form of templates and information.

### Q3.
 HTTP are a set of rules that lets web browsers and servers 'talk' to each other and exchange data across the web.
 
 HTTP request is kind of an information dictionary which has various values or attributes like request method, details about the client, the data sent by client to the server (in case of POST or PUT), the URL which client requested for and many other meta-data stuff which describes the exact need of the client to the server.
 
 HTTP response has a status number instead of a request method, for example 200 OK, 403 Forbidden, etc. The overall skeleton is similar to the request format. It also has meta-data to store the data formats of the response along with HTML, CSS, image, etc.

### Q4.
` GET` method is used when the client requests for something, an html template, for example. In this request type, **the backend sends data to the user.**

 `POST` method is used when the client fills a form or enters some values on the html page. In this request type, **the backend recieves the data from the user.**

### Q5.
 Status codes describes the response given by the backend to the client. For example, a 200 status code suggests that the response is generated without any errors, while a 403 status code means that the client is not allowed to access that webpage or data. 
 * **200**: client's request to the server succeeded
 * **302**: request redirected to a new URL
 * **404**: Information or data not found on the visited url
  * **500**: Server-side error (maybe errors in backend, reverseproxies configurations, or mismatch in protocol scheme)

### Q6.
 HTML, CSS and JavaScript mainly contribute to the frontend template, rather than functioning in backend incase of a Django application. HTML provides the structure, CSS controls the visual styling, and JavaScript adds interactive behavior.

### Q7.
A website remembers you between pages mainly by handing your browser a small piece of data, most often a *cookie* containing a unique **session ID**, that your browser automatically sends back with every new page request.

For example, you log in and add an item to cart in an e-commerce website, and thenhead on to the cart page to check out. In this process, a session ID formed on the previous page is passed on as a cookie on the current page, and this info inside session ID is passed in the new HTTP request sent to the server when requesting the new page. These cookies are stored as a type of cache memory allocated in the browser memory.

### Q8.
In Django, an incoming HTTP request moves through the Model-View-Template (MVT) pipeline in these steps:

1.  **Middleware:** Django wraps the raw request into an `HttpRequest` object and runs security and session checks.
2.  **URLs (`urls.py`):** The URL dispatcher matches the requested path to a route and forwards the request to the linked view.
3.  **Views (`views.py`):** The view processes the request, runs your business logic, and requests data if needed.
4.  **Models (`models.py`):** Django's ORM translates Python calls into SQL to fetch or save data in the database.
5.  **Templates (`.html`):** The view passes the data into a template, which renders a final HTML string.
6.  **Response:** Django wraps the HTML in an `HttpResponse`, passes it back through middleware, and sends it to the browser.

### Q9.
A CSRF (Cross-Site Request Forgery) token proves that a form submission actually came from your site's own page rather than a sneaky request triggered by another website

When you are logged into a site, your browser automatically attaches your session cookies to requests made to that domain. Without a CSRF token, a malicious site you visit could trick your browser into auto-submitting a form to that site, like changing your email or transferring funds, using your active session.
