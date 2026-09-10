TCP/IP and OSI Layers
So...what do the layers actually do?
I’ll be honest, this is where the OSI and TCP/IP models finally stop feeling like trivia and start feeling useful.


Up to this point, it’s easy to memorize layer names and pretend you understand networking. But when you actually watch a packet move, when you see data get wrapped, sent, opened, rewrapped, and forwarded, suddenly the whole thing clicks. Right? It goes from, “Cool, seven layers, I guess,” to “Ohhh...this is how the internet actually works.”

So in this lesson, I followed Johnny again as he tried to reach NetworkChuck Coffee over the network. Same simple goal, order some coffee. But under that simple click in a web browser is a whole stack of processes happening at lightning speed, each layer doing its job exactly the way it was designed to do. And that’s the big win here, you’re not just naming layers anymore, you’re seeing them in motion.

The models matter because they give every device a job. A switch doesn’t need to understand web traffic. A router doesn’t care what page Johnny wants. Each one just handles its layer and passes the rest along. That separation is wicked cool.

Click...and the stack goes to work
The moment Johnny types in the website, the application layer kicks in. In plain English, that’s the part where his web browser says, “Hey, I want this website.” In this case, the protocol is HTTPS, which is the secure version of HTTP, the language browsers use to talk to web servers. So before anything hits a cable, the request starts life as application data.

Now, hang on, sidebar for a moment. I used the OSI model to explain what was happening, even though in the real world we usually talk in terms of the TCP/IP model. Why? Because the OSI model gives me a little more detail, especially with those extra layers like session and presentation. In practice, those often get lumped into the application layer anyway, so don’t panic if that feels fuzzy right now. Okay, sidebar done.

From there, the data moves down to the transport layer, and this is where we decide how the data should travel.


Usually that means TCP or UDP. TCP is the reliable one, the one that says, “I’m going to make sure this gets there.” UDP is more like, “I’m sending it fast, good luck.” For a secure web request like this, TCP is in play, and we also see port 443, which tells the destination, “This traffic is for HTTPS.”

Encapsulation: envelope in envelope
This is the part I really want burned into your brain: encapsulation. That’s the process of taking data from one layer and wrapping it with that layer’s own information before handing it down to the next layer. I like to picture it like envelopes. You’ve got a message, then you put it in an envelope, then you put that envelope inside another envelope, and you keep going until it’s ready to be shipped. Absurd? A little. But also exactly what’s happening.

When the transport layer adds its header, that whole message becomes a segment. Then it gets handed down to layer 3, the network layer, where IP addressing lives. This is where the packet gets source and destination IP addresses, basically the full street addresses for where this data came from and where it’s trying to go. Once that layer 3 header is attached, we call it a packet.

Then we hit layer 2, the data link layer, and now we’re talking MAC addresses. These are not the end-to-end addresses like IPs. These are the local-delivery addresses used to get from one device to the next device. At this point, the packet gets wrapped in a layer 2 header and trailer, and now it becomes a frame. That frame is what actually gets sent over the physical network.

REAL WORLD TIP: If you ever get confused on an exam or in real life, ask yourself one question: “Am I dealing with end-to-end delivery or local hop-by-hop delivery?” If it’s end-to-end, think IP and layer 3. If it’s local delivery on the current network segment, think MAC address and layer 2. That one distinction clears up a shocking amount of confusion.

Switch vs. Router visibility
Once Johnny’s frame hits the switch, the switch does not care about the web request. It doesn’t care about TCP. It doesn’t care about HTTPS. It only looks at layer 2, because that’s its job. It opens the outermost envelope, checks the destination MAC address, looks in its MAC address table, and forwards the frame out the correct port. That’s it.

The router is different. When the frame reaches the router, the router checks the layer 2 destination and sees that the frame is for itself. So it strips off the layer 2 information, looks inside at layer 3, and now it’s reading the IP packet. This is where the router shines. It checks the destination IP, looks in its routing table, and decides where the packet should go next.

Now here’s the sneaky part that trips people up. The router can’t just forward the old frame as-is, because the old layer 2 information was only valid for the previous hop.


So the router has to re-encapsulate the packet into a brand-new frame with new source and destination MAC addresses for the next local segment. That’s huge. The IP addresses stay the same end-to-end, but the MAC addresses change hop by hop.

The server unwraps everything
Eventually, the frame makes it to the NetworkChuck Coffee server. And because that server follows the same model, it knows exactly what to do. First it checks layer 2 and confirms, “Yep, that MAC address is mine.” Then it de-encapsulates and checks layer 3, “Yep, that IP address is mine too.” Then layer 4, “Ah, TCP, port 443, this belongs to my secure web service.”

And finally, the request reaches the application layer, where the server understands what Johnny actually wants. He’s trying to load the website. He wants the homepage so he can buy coffee. So the server reads the request, builds a response, and then the whole process happens again in reverse, encapsulate, send, route, switch, receive, de-encapsulate.

That’s the key.

The devices in the middle don’t need the whole story. They just need the part of the story relevant to their layer. The switch forwards based on MAC. The router forwards based on IP. The server unwraps the whole thing because it’s the final destination. Once you see that, the models stop being abstract and start becoming a map you can actually use.

A quick gut-check before we go deeper
I also hit two quiz questions in this lesson, and honestly, they were a little spicy. The point wasn’t just to test memorization. It was to get you thinking about what each protocol and layer is responsible for. That’s how you survive networking exams, and more importantly, that’s how you troubleshoot in real life. Process of elimination becomes your best friend.

Here’s the short version of what I wanted you to walk away with:

Application layer is where user-facing network services begin, like web browsing with HTTPS.
Transport layer decides how data gets delivered, usually with TCP or UDP.
Network layer handles IP addressing and routing.
Data link layer handles MAC addressing and local delivery.
Encapsulation wraps data as it moves down the stack, and de-encapsulation unwraps it at the destination.
If all of this felt like a lot, good. Not because I want you overwhelmed, but because this is one of those moments where the fog starts to lift. You’re not just memorizing models anymore. You’re learning to see the network like a machine. And where we’re going next is deeper into those upper layers, application, presentation, session, transport, all the stuff that seemed vague before but is about to make a whole lot more sense.
