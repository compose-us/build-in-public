# Gathering Feedback

Hello y’all! 👋

Last time, we showed our prototype to the world and described it technically. If you haven’t seen the post, you can still check it out in [our Hackathon update](https://github.com/compose-us/build-in-public/blob/main/updates/2023-11-17%20Hackathon%20Update/README.md) to better understand what we are working on.

Since our last update, we mainly updated the styling and the user experience by hiding the QR code after the connection was made and showing the progress of the file transmission on both devices.

https://github.com/compose-us/build-in-public/assets/1767865/3ba4ea64-b619-4eeb-bcd8-db6df8656042

Our next step is to continue styling it and check out how to easily integrate it into existing products.

But before diving deeper into the integration part, let’s look back and see what we found out by talking about our idea and gathering feedback at various networking events. We’ll start with how we collected feedback, how we structured our conversations and share the actual results.

## Collecting feedback at events

Talking to strangers is hard. Attending networking events like meetups often helps to overcome the fear of approaching other humans. If you have seen a face multiple times, it’s a lot easier to talk to them. And since they are on similar events, you probably share some interest already.

For Jörn, the conversation usually started like this: “Imagine you need to submit an online form for whatever bureaucratic thing you have to do. After filling out some fields, you get tasked to upload a specific document or image. You know you either have it on your phone or could quickly take a picture of it. What do you do?”

Having such a conversation starter made it easy to follow-up on this and dive deeper into the topic and ultimately present our solution. Most people realized that this issue exists, lots of solutions are essentially workarounds and how our idea can help handling edge cases and improve the situation for users.

### General reception

People did face the issue we’re trying to solve. It’s not a problem they face every day, but whenever they do, they have to start thinking and find an ad-hoc solution. For most, this includes using some kind of cloud service, emailing the file to themselves or filling out the form again on their other device instead of continuing on the first.

We spoke to about 30 people, mainly developers themselves. Only two of them said they are using AirDrop. Some of the 30 knew about the feature but never used it. Or they knew about it, but aren’t fully invested in the Apple ecosystem to be able to use it. Everybody else used workarounds like sending emails or using a cloud provider to sync files before being able to continue with the form. We even got the suggestion to fill out the form again on the device that contains the file. Annoying, but it may sometimes be the fastest solution.

### Feedback for technical solution

To be fair, most events we attend are for developers. It’s not a big surprise to receive lots of questions about our technical solution. WebRTC seems to be of interest, but developers resigned to implement it without a really good use case. Due to its complexity, people resort to higher level abstractions for it. From what we saw, mostly conferencing tools are using WebRTC directly to get some performance gains out of it.

Many developers weren’t aware of key WebRTC features. The devices don’t necessarily need to be in the same internal network to share data. The security of the connection between peers is another good example for this: Even if there is a need for a server forwarding their traffic (a TURN server), the traffic is end-to-end encrypted.

### Feedback for business model

We haven’t shared much about our ideas on how to monetize our tool yet, but it’s obvious that we want to earn at least some money with this in the future. Initially, we saw two options:

Provide servers for initial handshakes and for allowing traffic from behind firewalls. Leads to some kind of usage fee, very easy to integrate for developers.

Create a browser extension, so users can enhance arbitrary forms with this. If extensions allow creating our own STUN and TURN servers for handshake and traffic routing, we may even be able to get this out for a fixed price.

Opening up on these rough ideas led to the suggestion of a third option, we didn’t see right away: Create a Wordpress plugin. This would enable us to use some kind of Wordpress marketplace for monetization. The handshake and traffic routing could be provided through a Wordpress instance, so we don’t even need to maintain an extra server for this. This might also be a way to find a bigger audience willing to integrate Flottform.

In the long run, we could provide integrations for different frameworks and either collect a few bucks or provide them for free, mostly using the technology as a marketing tool for acquiring projects. If you’ve followed our journey closely, you can tell we’re still prioritizing client work over Flottform.

## How to handle feedback

To be honest, we didn’t write down all the feedback directly. Putting the feedback into a spreadsheet is helpful though: After doing that, we can quickly see what common workarounds are. We can start asking other or more questions now to receive even better feedback in the future, like:

- “Do you remember where you had this issue”
- “How would you rate the technical solution / business model”
- “I know a similar idea that company XYZ uses”

It helps finding out what a person does as well. One time, we made an exception from the conversation starter and just showed the prototype, without explaining much. The person looked at it, said “that’s funny” and was about to leave. After a couple of seconds, the person went on to say “what the heck just happened?” and started asking lots of questions about how this works. It’s delightful to see someone actually care about our product, but it’s also hard to get information out of them, if they never thought about such a solution yet.

In the future, we’d like to gather more answers like

- Are we pursuing the right goals?
- Who is willing to pay for this?
- How much value do we provide to offer a fair price?

We will continue asking for feedback and will likely revisit this topic in the future.

## Key takeaways

Many thanks to everyone who offered their feedback and made suggestions! We really appreciate it and will continue to collect feedback to improve our idea. Our current key takeaways are:

- Everybody has faced the issue in the past and knows someone who struggles even more with it (parents, mostly)
- Idea is good, but people do not always understand how the peer to peer connection improves the situation
- Demoing works best

We already have two meetings planned for looking deeper into the integration of our script. Next time, we’ll talk about the integration into forms and what problems we face.

## Want to test drive our solution?

If you want, you can try out the integration with us as well: Drop us a message or send a direct message on LinkedIn to one of us and let us set something up! People who are willing to help should get something in return: We’d like to buy them a pizza (or something similar) for their time or make it very cheap and prioritize supporting them in the future. Let’s see what they want - or you, if you decide to connect with us! 😅

For now, we’ll stop this lengthy blog post and try to get faster writing these updates. If you want to follow along, watch and star our [build-in-public repository for updates](https://github.com/compose-us/build-in-public) and [the Flottform repository](https://github.com/compose-us/flottform) for implementation details. Connect with us on [LinkedIn](https://www.linkedin.com/company/compose-us/) / [Twitter / X](https://twitter.com/compose_us) or put your thoughts into our [discussion board](https://github.com/compose-us/build-in-public/discussions/5)!

Cheers,

[![Tamara](../tamara.png)](https://www.linkedin.com/in/tamara-bogantseva/) and [![Jörn](../joern.png)](https://www.linkedin.com/in/joern-bernhardt/)
