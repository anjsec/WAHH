The fundamental security problem with web applications — that all user input
is untrusted — gives rise to a number of security mechanisms that applications
use to defend themselves against attack.

The defense mechanisms employed by web applications comprise the following
core elements:
* Handling user access to the application’s data and functionality to prevent
users from gaining unauthorized access
* Handling user input to the application’s functions to prevent malformed
input from causing undesirable behavior
* Handling attackers to ensure that the application behaves appropriately
when being directly targeted, taking suitable defensive and offensive
measures to frustrate the attacker
* Managing the application itself by enabling administrators to monitor its
activities and confi gure its functionality

Because of their central role in addressing the core security problem, these
mechanisms also make up the vast majority of a typical application’s attack
surface.
If knowing your enemy is the fi rst rule of warfare, then understanding
these mechanisms thoroughly is the main prerequisite for being able to attacapplications effectively.

##### Handling User Access

A typical situation has
several different categories of user, such as anonymous users, ordinary authenticated
users, and administrative users. Furthermore, in many situations different
users are permitted to access a different set of data. For example, users of a web
mail application should be able to read their own e-mail but not other people’s.
Most web applications handle access using a trio of interrelated security
mechanisms:
* Authentication
* Session management
* Access control
A defect in
any single component may enable an attacker to gain unrestricted access to the
application’s functionality and data.

##### Authentication
Authenticating a user involves establishing
that the user is in fact who he claims to be. Without this facility, the application
would need to treat all users as anonymous — the lowest possible level of trust.
The majority of today’s web applications employ the conventional authentication
model, in which the user submits a username and password, which
the application checks for validity.
When security requirements are higher still, other authentication models
may be used, based on client certifi cates, smartcards, or challenge-response
tokens. In addition to the core login process, authentication mechanisms often
employ a range of other supporting functionality, such as self-registration,
account recovery, and a password change facility.

##### Session Management

The next logical task in the process of handling user access is to manage the
authenticated user’s session. After successfully logging in to the application, the
user accesses various pages and functions, making a series of HTTP requests from
his browser. At the same time, the application receives countless other requests
from different users, some of whom are authenticated and some of whom are
anonymous. To enforce effective access control, the application needs a way to
identify and process the series of requests that originate from each unique user.

Virtually all web applications meet this requirement by creating a session for
each user and issuing the user a token that identifi es the session. The session
itself is a set of data structures held on the server that track the state of the user’s
interaction with the application. The token is a unique string that the application
maps to the session. When a user receives a token, the browser automatically
submits it back to the server in each subsequent HTTP request, enabling
the application to associate the request with that user. HTTP cookies are the
standard method for transmitting session tokens, although many applications
use hidden form fi elds or the URL query string for this purpose. If a user does
not make a request for a certain amount of time, the session is ideally expired.

In terms of attack surface, the session management mechanism is highly
dependent on the security of its tokens. The majority of attacks against it seek to
compromise the tokens issued to other users. If this is possible, an attacker can
masquerade as the victim user and use the application just as if he had actually
authenticated as that user. The principal areas of vulnerability arise from defects
in how tokens are generated, enabling an attacker to guess the tokens issued to
other users, and defects in how tokens are subsequently handled, enabling an
attacker to capture other users’ tokens.
A small number of applications dispense with the need for session tokens by
using other means of reidentifying users across multiple requests. If HTTP’s
built-in authentication mechanism is used, the browser automatically resubmits
the user’s credentials with each request, enabling the application to identify the
user directly from these. In other cases, the application stores the state information
on the client side rather than the server, usually in encrypted form to
prevent tampering.

#### Access Control
Access control is a security technique that regulates who or what can view or use resources in a computing environment. ... Physical access control limits access to campuses, buildings, rooms and physical IT assets. Logical access control limits connections to computer networks, system files and data.
The access control mechanism usually needs to implement some fi ne-grained
logic, with different considerations being relevant to different areas of the
application and different types of functionality. An application might support
numerous user roles, each involving different combinations of specifi c privileges.
Individual users may be permitted to access a subset of the total data held within
the application. Specifi c functions may implement transaction limits and other
checks, all of which need to be properly enforced based on the user’s identity.
Because of the complex nature of typical access control requirements, this
mechanism is a frequent source of security vulnerabilities that enable an attacker to gain unauthorized access to data and functionality.

#### Handling User Input
Input-based vulnerabilities can arise anywhere within an application’s functionality,
and in relation to practically every type of technology in common use.
“Input validation” is often cited as the necessary defense against these attacks.
However, no single protective mechanism can be employed everywhere, and
defending against malicious input is often not as straightforward as it sounds.

#### Varieties of Input

value to some of its user base.
In addition to the various kinds of input that users enter using the browser
interface, a typical application receives numerous items of data that began their
life on the server and that are sent to the client so that the client can transmit
them back to the server on subsequent requests. This includes items such as
cookies and hidden form fi elds, which are not seen by ordinary users of the
application but which an attacker can of course view and modify. In these cases,
applications can often perform very specifi c validation of the data received. For
example, a parameter might be required to have one of a specifi c set of known
values, such as a cookie indicating the user’s preferred language, or to be in a
specifi c format, such as a customer ID number. Furthermore, when an application
detects that server-generated data has been modifi ed in a way that is not
possible for an ordinary user with a standard browser, this often indicates
that the user is attempting to probe the application for vulnerabilities. In these
cases, the application should reject the request and log the incident for potential
investigation

##### Approaches to Input Handling
Different approaches are often preferable for different situations
and different types of input, and a combination of approaches may sometimes
be desirable.

