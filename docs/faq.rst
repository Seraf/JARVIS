Frequently Asked Questions
==========================

.. contents:: FAQ

Is LISA open-source ?
---------------------

Yes. LISA is 100% open-source, including all APIs.

And in the future, even if I create an enterprise with LISA, it will stay opensource and free.

Can I fork it ?
---------------

Yes you can fork it if you want. Everything will be opensourced, even the "appstore".
But of course, I encourage everyone to contribute instead of spreading smart people.

Is LISA full local mode or does it need an Internet connection ?
----------------------------------------------------------------

LISA is actually needing an Internet connection. I work on it to have something fully working even if your
connection is broken.

LISA need internet at least for his client (because speech recognition is online) and to use Wit Engine
on the server side. Wit is also working on a local server for Wit. Once it will be available, it will be
backported in LISA as soon as possible.

Which Speech Engine do you use ?
--------------------------------
Even if it is one of the most important part of the project, I don't want to focus on it.
The actual Linux Client use pocketsphinx to detect a keyword (the name of the bot).
It's a trigger to launch the speech recognition by voice. LISA will listen and stream each
chunk to Wit Speech API. It's a online webservice and they use many speech engine in backend
to do the speech recognition. They plan to create free accoustic models and use (in the future)
only opensource speech engine. They are partner of CMUSphinx.

Not convinced ? Don't want to see your voice go outside your home ?

Well, LISA was built to let the user choose his speech engine. You can create an irc bot client,
a hangout bot, a jabber bot, a voice client which use Dragon Natural Speech, Windows Grammar,
Android Speech Engine or whatever. The choice is yours, just send a sentence to LISA.

Don't forget that smaller is the device where is hosted the client, less will be the computing capacity
to do speech recognition in local mode. But don't be worry, I want for myself something in local and working
without internet connection.

Why LISA use mongodb as database ?
----------------------------------

I am a DevOps, then when I code, I always think about how will it work in production. Is it scalable ?
Mongodb let LISA to scale and support loss of a server. The database can be distribued accross your
clients for example. The NoSQL technology allow developers to build plugins easily.

As plugins and configuration are stored in the mongodb database, you can scale the LISA server with
a load balancer.

The only problem is a lack of support for ARM. But there's a ticket opened on their JIRA issue tracker.

Can I install LISA on a Raspberry Pi ?
--------------------------------------
Quick answer : Yes.

Long answer : RPI is an ARM architecture and actually Mongodb is unsupported officially.
So it isn't packaged for raspbian for example. But you should be able to compile it (take ~7hours).

There's a ticket already opened on their JIRA for ARM support, and they are working on it.

By now, I suggest to run mongodb (and the LISA server) in a virtual machine or a dedicated x86 server.


What ports should I open on my firewall ?
-----------------------------------------

LISA use by default the port 10042 to communicate between client and server, and port 8000 for the webserver.

Can I do Home Automation with this project ?
--------------------------------------------
Short answer : No. LISA allow you to create a bridge between your connected objects and your home automation box.
LISA can also handle some "intelligency" to execute orders on your home automation box, but it won't replace
an automation box.

Why LISA is written in Python ?
-------------------------------
Firstly, I wanted to learn this language since a long. The code may be not perfect so don't hesit to send a patch.
I love Python because there's a lot of API written in Python language and as LISA is a built to connect API between them
it was logic to use a language easy to learn and easy to use.
