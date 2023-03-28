
## WEB SERVER


A web server is software and hardware that uses HTTP (Hypertext Transfer Protocol) and other protocols to respond to client requests made over the World Wide Web. The main job of a web server is to display website content through storing, processing and delivering webpages to users


The main job of a web server is to display the website content. If a web server is not exposed to the public and is used internally, then it is called Intranet Server. When anyone requests for a website by adding the URL or web address on a web browser’s (like Chrome or Firefox) address bar (like www.eport.com), the browser sends a request to the Internet for viewing the corresponding web page for that address. A Domain Name Server (DNS) converts this URL to an IP Address (For example 192.168.216.345), which in turn points to a Web Server.

Functions of a Web Server


To understand all aspects of a web server, it is important to start with an understanding of its various functions.

Web servers have the following functions in general:

Web servers store and configure all website data. This is done to protect data from unauthorized users.
Web servers have the prime responsibility to enable accessibility to hosted websites. This includes the availability of back-end database server services and more.

When potential clients around the globe are trying to access your website, your website’s web server would serve them accordingly. Such potential clients and visitors are known as end users and their access requests are known as end-user requests.

Web servers help in controlling the bandwidth; they are equipped to minimize excess network traffic, thus regulating the overall traffic in the network. This feature of web servers prevents downtime to a great extent. Downtime is usually caused by surplus web traffic.

The presence of a web server enables the creation of dynamic web pages in popular scripting languages such as Perl, Ruby, Python, and others.


How Does a Web Server Work?

A web browser uses HTTP to request a file hosted on a web server. The HTTP server accepts this request, finds the file, and then sends it back to the browser using HTTP.  Let us take a look at all the steps involved in the process:

A user specifies the URL they want to access in the address bar.
The browser fetches the IP address of the domain name. This would take the web browser to the web server.
The browser requests the file from the web server using HTTP.
The web server will send back the requested file via HTTP. If, in case, the file does not exist, an error message will be sent.
The browser displays the web page.

Examples of Web Server Uses

Web servers are a component of a larger internet and intranet package. They can be used for:

Sending and receiving emails
Downloading requests for file transfer protocol (FTP) files

Building and publishing web pages
Server-side scripting is also supported on a lot of web servers. It employs scripts on a web server and can help personalize the response for the clients. 

The server machine is used to run server-side scripting. The process uses various scripting languages such as Hypertext Preprocessor (PHP), Active Server Pages (ASP), etc. HTML documents can be created dynamically by using the same process.


Types of Web Servers


Apache
Launched in 1996 and is currently maintained by the Apache Foundation, Apache Web Server is one of the most popular web servers in the world today. It is a freeware. It is one of the top web server examples to be compatible with platforms such as Linux, Windows, Mac, and more.

IIS
Known widely with its abbreviation, Internet Information Services (IIS) is a web server that is owned by Microsoft. IIS comes with the Windows Server Operating System and can be configured via a graphic interface.

NGINX
NGINX was developed in 2002 by Igor Sysoev. It is a web server that works as a proxy server as well. This means that it, just like Apache, can work along with another web server. Its primary job is to handle hundreds of concurrent connections.


Apache Tomcat
Apache Tomcat is a free web server that specializes in Java Servlets. Apache Tomcat is popularly known as a Java container. It can work under Port 8080 and supports PHP, ASP.net, Perl, Python, and more.

lighttpd
lighttpd was developed in 2003. This web server requires low memory and CPU and disk space. Web cameras, internet routers, and other things of a similar nature use lighttpd as their web server.


Static Web Server vs Dynamic Web Server

Web servers can serve both static and dynamic content. Static content is shown as it is, while dynamic content keeps changing.

A static web server has a computer along with an HTTP software. When the server sends the hosted files to the browser, they are sent without any changes.

On the other hand, a dynamic web server has a computer and other software such as a database and an application server. The application server can update the hosted files at any time before they are sent to the browser. This web server can also generate content whenever it is requested from the database. This provides flexibility but also makes the process more complex.

Web Server Architecture

Web server architecture is the layout of a web server. These are developed, designed, and deployed based on the web server architecture. All the essential components of a web server, which are required for delivering web-server-based operations and services, are defined in the architectural layout.

There are certain parameters that are defined in the web server architecture, including:

The physical capacity of the server. This includes storage, memory, and computing power.
The quality of the server and its performance. This includes throughput, latency, and low memory use.
The application tiers. This includes the different types of applications that are deployed on the server.
 The platform that is supported.
 The operating system.
 The network or internet connectivity.
There are two approaches to web server architecture:



Concurrent Approach

Single-process-event-driven Approach



Concurrent Approach
With the concurrent approach, a web server can handle multiple client requests at the same time. One of the following three methods can be used to achieve that:

Multi-process
Multithreaded
Hybrid
Multi-process


A single parent process creates various single-threaded child processes and then distributes all the incoming requests to the child processes. All the child processes handle one request at a time. The parent process is responsible for monitoring the load and deciding if a process needs to be forked or filled.

Multithreaded
Multiple single-threaded processes are created to handle various requests.

Hybrid

This approach combines the above two approaches. Multiple processes are created that initiate multiple threads. One thread handles one connection.

Single-process-event-driven Approach

In the single-process-event-driven (SPED) approach, a single process performs all client processing and activity, in an event-driven manner. It uses a single event-driven server process, and is responsible for processing multiple HTTP requests concurrently.

Web Server Security

It is very important to keep your web server secure. With the absence of web server security, your web server is vulnerable to various attacks such as DoS attacks, SSoS attacks, SQL injections, unpatched software, cross-site scripting, and much more.

You can protect your web server in the following ways:

Keep only required services on your server. Having too many services on your web server can open portals. This can enable hacking activities in the long run. An additional benefit of removing unnecessary services is that it will improve the overall website functionality.

By having separate environments for development, testing, and production, you can reduce the risk of breach. Preferably, separate environments should be kept private.

Automate backups and install a firewall. A firewall will come in handy even if all your security systems are compromised. By automating backup daily, you can preserve data for the long run. This will be useful even when your system is compromised beyond repair.

