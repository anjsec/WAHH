
Chapter 1, “Web Application (In)security,” describes the current state of security
in web applications on the Internet today. Despite common assurances, the
majority of applications are insecure and can be compromised in some way with
a modest degree of skill. Vulnerabilities in web applications arise because of a
single core problem: users can submit arbitrary input. This chapter examines the
key factors that contribute to the weak security posture of today’s applications.
It also describes how defects in web applications can leave an organization’s
wider technical infrastructure highly vulnerable to attack.
 
### "The Evolution of Web Applications"
In the early days of the Internet, the World Wide Web consisted only of web
sites. These were essentially information repositories containing static documents.
Web browsers were invented as a means of retrieving and displaying
those documents. The fl ow of interesting information
was one-way, from server to browser. Most sites did not authenticate users,
because there was no need to. Each user was treated in the same way and was
presented with the same information. Any security threats arising from hosting
a website were related largely to vulnerabilities in web server software (of
which there were many). If an attacker compromised a web server, he usually
would not gain access to any sensitive information, because the information
held on the server was already open to public view. Rather, an attacker typically
would modify the fi les on the server to deface the web site’s contents or use the
server’s storage and bandwidth to distribute “warez.”

The majority of sites on the web are in fact applications. They
are highly functional and rely on two-way fl ow of information between the
server and browser. They support registration and login, fi nancial transactions search, and the authoring of content by users. The content presented to users
is generated dynamically on the fl y and is often tailored to each specifi c user.
Much of the information processed is private and highly sensitive. Security,
therefore, is a big issue. No one wants to use a web application if he believes
his information will be disclosed to unauthorized parties.

 To deliver their core functionality, web applications normally require
connectivity to internal computer systems that contain highly sensitive data and
that can perform powerful business functions.
[EXAMPLE]
Fifteen years ago, if you wanted
to make a funds transfer, you visited your bank, and the teller performed the
transfer for you; today, you can visit a web application and perform the transfer
yourself. An attacker who compromises a web application may be able to steal
personal information, carry out fi nancial fraud, and perform malicious actions
against other users.

##### Common Web Application Functions

Web applications have been created to perform practically every useful function
you could possibly implement online. Here are some web application functions
that have risen to prominence in recent years:
* Shopping (Amazon)
* Social networking (Facebook)
* Banking (Citibank)
* Web search (Google)
* Auctions (eBay)
* Gambling (Betfair)
* Web logs (Blogger)
* Web mail (Gmail)
* Interactive information (Wikipedia)

Applications that are accessed using a computer browser increasingly overlap
with mobile applications that are accessed using a smartphone or tablet. Most
mobile applications employ either a browser or a customized client that uses
HTTP-based APIs to communicate with the server. Application functions and
data typically are shared between the various interfaces that the application
exposes to different user platforms.
In addition to the public Internet, web applications have been widely adopted
inside organizations to support key business functions. Many of these provide
access to highly sensitive data and functionality:
+ HR applications allowing users to access payroll information, give and
receive performance feedback, and manage recruitment and disciplinary
procedures.
+ Administrative interfaces to key infrastructure such as web and mail
servers, user workstations, and virtual machine administration.
+ Collaboration software used for sharing documents, managing workfl
ow and projects, and tracking issues. These types of functionality often
involve critical security and governance issues, and organizations often
rely completely on the controls built into their web applications.
+ Business applications such as enterprise resource planning (ERP) software,
which previously were accessed using a proprietary thick-client application,
can now be accessed using a web browser
In all these examples, what are perceived as “internal” applications are increasingly
being hosted externally as organizations move to outside service providers
to cut costs. In these so-called cloud solutions, business-critical functionality
and data are opened to a wider range of potential attackers, and organizations
are increasingly reliant on the integrity of security defenses that are outside of their control.

##### Benefits of Web Applications
+ HTTP, the core communications protocol used to access the World Wide
Web, is lightweight and connectionless. This provides resilience in the
event of communication errors and avoids the need for the server to
hold open a network connection to every user, as was the case in many
legacy client/server applications. HTTP can also be proxied and tunneled
over other protocols, allowing for secure communication in any network
confi guration.
+ Every web user already has a browser installed on his computer and
mobile device. Web applications deploy their user interface dynamically
to the browser, avoiding the need to distribute and manage separate
client software, as was the case with pre-web applications. Changes to
the interface need to be implemented only once, on the server, and take
effect immediately.
+ Today’s browsers are highly functional, enabling rich and satisfying
user interfaces to be built. Web interfaces use standard navigational and
input controls that are immediately familiar to users, avoiding the need
to learn how each individual application functions. Client-side scripting
enables applications to push part of their processing to the client side, and
browsers’ capabilities can be extended in arbitrary ways using browser
extension technologies where necessary.
+ The core technologies and languages used to develop web applications are
relatively simple. A wide range of platforms and development tools are
available to facilitate the development of powerful applications by relative
beginners, and a large quantity of open source code and other resources
is available for incorporation into custom-built applications.

###### Web Application Security

The most serious attacks against web applications are those that expose
sensitive data or gain unrestricted access to the back-end systems on which
the application is running. High-profi le compromises of this kind continue
to occur frequently. For many organizations, however, any attack that causes
system downtime is a critical event. Application-level denial-of-service attacks
can be used to achieve the same results as traditional resource exhaustion
attacks against infrastructure. However, they are often used with more subtle
techniques and objectives. They may be used to disrupt a particular user or
service to gain a competitive edge against peers in the realms of fi nancial trading,
gaming, online bidding, and ticket reservations.

##### “This Site Is Secure”
In fact, the majority of web applications are insecure, despite the widespread
usage of SSL technology and the adoption of regular PCI scanning.
+ Broken authentication (62%) — This category of vulnerability encompasses
various defects within the application’s login mechanism, which
may enable an attacker to guess weak passwords, launch a brute-force
attack, or bypass the login.
+ Broken access controls (71%) — This involves cases where the application
fails to properly protect access to its data and functionality, potentially
enabling an attacker to view other users’ sensitive data held on the server
or carry out privileged actions.
+ SQL injection (32%) — This vulnerability enables an attacker to submit
crafted input to interfere with the application’s interaction with back-end
databases. An attacker may be able to retrieve arbitrary data from the
application, interfere with its logic, or execute commands on the database
server itself.
+ Cross-site scripting (94%) — This vulnerability enables an attacker to
target other users of the application, potentially gaining access to their
data, performing unauthorized actions on their behalf, or carrying out
other attacks against them.
+ Information leakage (78%) — This involves cases where an application
divulges sensitive information that is of use to an attacker in developing
an assault against the application, through defective error handling or
other behavior.
+ Cross-site request forgery (92%) — This fl aw means that application
users can be induced to perform unintended actions on the application
within their user context and privilege level. The vulnerability allows a
malicious web site visited by the victim user to interact with the application
to perform actions that the user did not intend.

##### SSL is an excellent technology that protects the confidentiality and integrity
of data in transit between the user’s browser and the web server. It helps defend
against eavesdroppers, and it can provide assurance to the user of the identity of
the web server he is dealing with. But it does not stop attacks that directly target
the server or client components of an application, as most successful attacks do.
Specifi cally, it does not prevent any of the vulnerabilities just listed, or many
others that can render an application critically exposed to attack. Regardless of
whether they use SSL, most web applications still contain security fl aws.

#### The Core Security Problem: Users Can Submit
Arbitrary Input

Users are not restricted to using only a web browser to access the application.
Numerous widely available tools operate alongside, or independently of,
a browser to help attack web applications. These tools can make requests
that no browser would ordinarily make and can generate huge numbers
of requests quickly to fi nd and exploit problems.


The majority of attacks against web applications involve sending input to the
server that is crafted to cause some event that was not expected or desired by
the application’s designer. Here are some examples of submitting crafted input
to achieve this objective:

+ Changing the price of a product transmitted in a hidden HTML form fi eld
to fraudulently purchase the product for a cheaper amount
+ Modifying a session token transmitted in an HTTP cookie to hijack the
session of another authenticated user
+ Removing certain parameters that normally are submitted to exploit a
logic fl aw in the application’s processing
+ Altering some input that will be processed by a back-end database to inject
a malicious database query and access sensitive data

Needless to say, SSL does nothing to stop an attacker from submitting crafted
input to the server. If the application uses SSL, this simply means that other users
on the network cannot view or modify the attacker’s data in transit. Because
the attacker controls her end of the SSL tunnel, she can send anything she likes
to the server through this tunnel. If any of the previously mentioned attacks
are successful, the application is emphatically vulnerable, regardless of what
its FAQ may tell you.

##### Key Problem Factors

The core security problem faced by web applications arises in any situation
where an application must accept and process untrusted data that may be malicious.


##### Underdeveloped Security Awareness


Although awareness of web application security issues has grown in recent
years, it remains less well-developed than in longer-established areas such as
networks and operating systems. Although most people working in IT security
have a reasonable grasp of the essentials of securing networks and hardening
hosts, widespread confusion and misconception still exist about many of the
core concepts involved in web application security. A web application developer’s
work increasingly involves weaving together tens, or even hundreds,
of third-party packages, all designed to abstract the developer away from the
underlying technologies. It is common to meet experienced web application
developers who make major assumptions about the security provided by their
programming framework and to whom an explanation of many basic types of
fl aws comes as a revelation.

##### Custom Development


Most web applications are developed in-house by an organization’s own staff
or third-party contractors. Even where an application employs well-established
components, these are typically customized or bolted together using new code.
In this situation, every application is different and may contain its own unique
defects. This stands in contrast to a typical infrastructure deployment, in which
an organization can purchase a best-of-breed product and install it in line with
industry-standard guidelines.

##### Deceptive Simplicity

A prominent trend in recent years has been the use of application frameworks
that provide ready-made code components to handle numerous common areas
of functionality, such as authentication, page templates, message boards, and
integration with common back-end infrastructure components. Examples of these
frameworks include Liferay and Appfuse. These products make it quick and
easy to create working applications without requiring a technical understanding
of how the applications work or the potential risks they may contain. This also
means many companies use the same frameworks. Thus, when a vulnerability
is discovered, it affects many unrelated applications.

##### Rapidly Evolving Threat Profile 

Particularly on the client side, it is common for
the accepted defenses against a particular attack to be undermined by research
that demonstrates a new attack technique. A development team that begins a
project with a complete knowledge of current threats may have lost this status
by the time the application is completed and deployed.

##### Resource and Time Constraints

In the balancing of competing priorities, the need to produce a stable and
functional application by a deadline normally overrides less tangible security
considerations. A typical small organization may be willing to pay for only a
few man-days of consulting time to evaluate a new application. A quick penetration
test will often fi nd the low-hanging fruit, but it may miss more subtle
vulnerabilities that require time and patience to identify.

##### Overextended Technologies 
As the expectations placed on web application functionality have
rapidly evolved, the technologies used to implement this functionality have
lagged behind the curve, with old technologies stretched and adapted to meet
new requirements. Unsurprisingly, this has led to security vulnerabilities as
unforeseen side effects emerge.

##### Increasing Demands on FunctionalityModern sites may include password
recovery, username recovery, password hints, and an option to remember the
username and password on future visits. Such a site would undoubtedly be
promoted as having numerous security features, yet each one is really a selfservice
feature adding to the site’s attack surface.

##### The New Security Perimeter
Web applications have changed all this. For an application to be accessible
by its users, the perimeter fi rewall must allow inbound connections to the
server over HTTP or HTTPS. And for the application to function, the server
must be allowed to connect to supporting back-end systems, such as databases,
mainframes, and fi nancial and logistical systems. These systems often lie at
the core of the organization’s operations and reside behind several layers of
network-level defenses.

A second way in which web applications have moved the security perimeter
arises from the threats that users themselves face when they access a vulnerable
application. A malicious attacker can leverage a benign but vulnerable web
application to attack any user who visits it. If that user is located on an internal
corporate network, the attacker may harness the user’s browser to launch an
attack against the local network from the user’s trusted position. Without any
cooperation from the user, the attacker may be able to carry out any action that
the user could perform if she were herself malicious. With the proliferation of
browser extension technologies and plug-ins, the extent of the client-side attack
surface has increased considerably.


##### The Future of Web Application Security

Various recent trends in technology have somewhat altered the landscape of
web applications. Popular consciousness about these trends exists by means of
various rather misleading buzzwords, the most prominent of which are these:

* Web 2.0 — This term refers to the greater use of functionality that enables
user-generated content and information sharing, and also the adoption
of various technologies that broadly support this functionality, including
asynchronous HTTP requests and cross-domain integration.

* Cloud computing — This term refers to greater use of external service
providers for various parts of the technology stack, including application
software, application platforms, web server software, databases, and
hardware. It also refers to increased usage of virtualization technologies
within hosting environments.



 










