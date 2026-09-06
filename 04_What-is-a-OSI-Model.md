What is TCP/IP and OSI?
Networking: Built on Agreement
I want you to pause for a second and appreciate something we totally take for granted. A Raspberry Pi can talk to an iPhone.


A Windows laptop can open a website hosted on a Linux server. You can send a photo from one device to another and not even think twice about it. That feels normal now, but once upon a time, that was absurdly difficult.

Here's the contrarian part. Devices talking to each other is not the natural state of technology. It's the exception we had to invent. Early on, companies built their own computers and then built their own ways for those computers to communicate. Which sounds fine until you realize that meant one vendor's devices often couldn't talk to anyone else's stuff. Same idea as trying to plug the wrong charging cable into your phone. It just doesn't fit.

So when we talk about TCP/IP and OSI, we're really talking about the answer to that problem. These are network models, meaning organized ways to describe how communication should happen. Not just, "Hey, send data," but how that data gets packaged, addressed, transmitted, received, and understood. That's the magic right there.

A Look Back at Early Networking
Back in the 1960s, people started asking a question that changed everything: "What if computers could communicate?" That led to ARPANET, one of the first major networks, created by the U.S. Department of Defense. It was revolutionary because it proved the idea could work, computers could send data across a network instead of living as isolated islands.

But hang on, sidebar for a moment. When I say they had a network, I don't mean they had everything figured out the way we do now. I mean they had the beginning of the idea. They had concepts like packet switching, which is the idea of breaking data into smaller chunks called packets and sending them across a network. Super cool...but still messy.

The problem was that as the idea spread, every company wanted to build its own networking system. IBM had one way. Other vendors had different ways. Those systems were often proprietary, meaning they only worked with that company's products. So computers weren't just different machines, they were speaking completely different languages. Right? That's a problem if the whole point is communication.

"Without standards, networking would've stayed a bunch of isolated islands. Cool tech, sure, but useless at scale."

Eventually, everyone realized this was kind of a travesty. If networking was going to matter, we needed shared standards. We needed rules everybody could agree on, so no matter who made the computer, the network behavior would be familiar and compatible. That's where the models came in.

TCP/IP is the one we actually use
The model that won is TCP/IP, also called the TCP/IP stack. This is the practical, real-world set of standards modern devices use to communicate. Every major operating system, every router, every phone, every server, they all live here. If devices can talk on today's networks, TCP/IP is almost certainly part of the reason why.

Now, to make all of this easier to understand, we divide the communication process into layers. That's the key.


Instead of one giant blob of "networking stuff," we separate the job into stages. One layer handles the physical connection, another deals with addressing, another handles reliable delivery, and another handles the applications you actually use.

In the version you'll commonly use for CCNA, I break TCP/IP into layers that line up like this:

Physical: cables, signals, network cards, the actual electrical or wireless transmission
Data Link: MAC addresses and local network communication
Network: IP addresses and routing between networks
Transport: protocols like TCP and UDP, plus port numbers
Application: the services and protocols apps use, like web traffic
If you've already been thinking about switches, routers, and IP addresses, you're already touching these layers. A switch mostly lives at Layer 2, the Data Link layer. A router works at Layer 3, the Network layer. And if we're talking cables and raw signal transmission, that's Layer 1, the Physical layer. You see what just happened there? The model gives us a way to organize the chaos.

So Why Still Discuss OSI?
This is the weird part. TCP/IP won, but OSI is still everywhere in networking conversations. OSI stands for Open Systems Interconnection, and it's another layered model for describing network communication. It didn't become the practical standard the way TCP/IP did, but it absolutely won the terminology war. That's why network engineers still talk in OSI layers all the time.

The OSI model has seven layers instead of five:

7. Application

6. Presentation

5. Session

4. Transport

3. Network

2. Data Link

1. Physical

Now, you might be thinking, "Okay, if TCP/IP is what we actually use, why bother?" Here's why: when engineers troubleshoot, we constantly use OSI language. We say things like, "That's a Layer 1 issue," meaning a physical problem. Or, "That's Layer 7," meaning it's probably an application problem. Even when the real-world traffic is using TCP/IP, the OSI model gives us a cleaner troubleshooting vocabulary.

And honestly, for Layers 1 through 4, they map over pretty cleanly. Physical, Data Link, Network, Transport, same basic concepts. The main difference is at the top, where OSI separates Session and Presentation into their own layers, while TCP/IP tends to roll that functionality into the Application layer. So the ideas don't disappear. They're just grouped differently.

REAL WORLD TIP: When I'm troubleshooting, I don't start by panicking and saying, "The network is broken." I start by asking, "What layer is failing?" If the cable is unplugged, that's Layer 1. If the switch can't forward frames, that's Layer 2. If the app won't load but connectivity is fine, that's probably Layer 7. This one habit will make you look way more experienced than you feel.

This is why the models matter
I know this can feel abstract at first. Layers, models, standards... it can sound like theory for the exam.


But this stuff becomes incredibly practical the moment something breaks. Because if you don't have a framework, every problem feels random. With the models, you get a roadmap.

Let's say NetworkChuck Coffee can't process online orders. Do we blame the app? Maybe. But maybe the server has the wrong IP address. Maybe the switch port is misconfigured. Maybe the cable is dead. See the point? The models help me isolate the problem instead of just wildly guessing and rebooting things until I cry into my espresso.

That's why I want you to know both models. Know TCP/IP because it's the one devices actually use. Know OSI because it's the language network engineers actually speak. For exams, you need both. For real life, you need the troubleshooting mindset they give you.

The Big Takeaway
Let me put this all together. TCP/IP is the practical model that made universal networking possible. OSI is the conceptual model we still use constantly to describe and troubleshoot what happens on a network. One powers the communication. The other gives us the language to understand it.

And once you start seeing networking in layers, everything gets clearer. Switches make more sense. Routers make more sense. Applications failing in weird ways start to make more sense. Right now, this is the foundation. Next, things are about to get quite a bit deeper, because the real fun starts when we actually follow a packet through those layers and watch what happens at each step.
