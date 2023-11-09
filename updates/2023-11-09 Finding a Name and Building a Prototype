# Finding a Name and Building a Prototype

Hello y’all!

It’s been over two weeks already since [our last update where we promised to find a name and build a prototype](https://github.com/compose-us/build-in-public/blob/main/updates/2023-10-23%20Defining%20our%20mission%20-%20Improve%20Web%20Form%20File%20Uploads/README.md).

## Finding a name

Trying to find a perfect name for our tool, we used help from AI tools, like [ChatGPT](https://chat.openai.com/), [ahrefs Free AI Product Name Generator](https://ahrefs.com/writing-tools/product-name-generator). The process led to funny conversations but didn’t result in a name for our tool. The recommended names were either too boring, too simple or the domain names were all taken. After the initial brainstorming round, we were left with six contenders.

Building the prototype should be our priority, so we had to decide on the name quickly. Every minute that we haven’t created a repository due to not finding a name counts as lost: We want to validate our ideas with people and the name shouldn’t be the deciding factor. Seeing the time passing quickly, we settled on “Flottform”, since we already owned the domain and it fits well enough for now. We can always change it later, anyways.

Why use a name we’re not 100% happy with? We have seen indecisiveness can really put the brakes on a project. We've seen it with clients: We've noticed with our clients, those who get caught in a loop of hesitation tend to lag behind, while the go-getters who make quick and smart decisions are the ones who end up leading the pack. So let us try to be one of those who swiftly decide!

## Building a prototype

After finding the name, we finally got around to developing a prototype of our idea! Most of the time was actually researching how WebRTC works. As we’ve mentioned before, we wanted to try this out and see whether it’s a good fit for our use-case. Since this took quite a while to figure out, we should document what we’ve found out so far.

### Using WebRTC is not a stand-alone solution

While WebRTC solves a lot of problems on how to handle peer-to-peer connections properly, it is not easily set up with a one-liner. Considering we have two peers who shall talk to each other, they both need to get information from each other before being able to actually have a channel to transmit something.

It is possible to copy and paste that information from one machine to the other, but this leads to the same problem we initially wanted to solve! A proposed solution for this are STUN servers, that organize the initial handshake between the peers. If they cannot connect to each other directly, a fallback with so-called TURN servers exists.

To know whether they can connect to each other directly or need to use a TURN server, the peers need to exchange ICE (Interactive Connectivity Establishment) candidates after sending and receiving offers for a peer connection itself. Ultimately, this is quite a long list of things to be done and as mentioned, there are tools like STUN and TURN servers to improve the development experience.

### Creating a proof of concept

To check the feasibility of our prototype, we didn’t want to set up STUN and TURN servers though. In our experience, if you don’t have something working already and are adding multiple layers of complexity at once, it’s very easy to get stuck: You can’t always tell whether the issue lies in the code or in some configuration of a tool, API or whatever else that has been used. If you don’t know the dependencies already, it can be easy to end up in long debugging sessions. Being able to reduce the complexity of how things can fail usually helps. Our intention right now is to only check whether sending a file through a data channel works and that can be connected to a form data field.

The most basic version we came up with was this: Create a form with file fields, let a script run over it and add a button to create a channel for another device. Clicking each button creates a link with the initial offer and ICE candidates being put into the hash of a link. Sending that link to another device is currently a manual step but could be done through a QR code. It also creates a text field that waits for the ICE candidates from the other device to be pasted in. When the other device accesses the link, it generates that list of ICE candidates and lets you copy them. While this is still a manual process, it shows that a peer connection is possible.

With this in place, it will be easier to iterate and make the next steps possible:

1. Send an actual file from device B through the data channel to device A
2. Ensure posting the form on device A after receiving the file from device B works
3. Simplify the initial connection process

For people interested in the actual tech, check out [the Flottform repository]() to follow the state of our implementation. Here is [the tag that reflects the current state]() so you can see the code we are referring to as a permanent link, even if we decide to completely change architecture, tech stack, etc. in the future.

## Next steps

We will meet at the Bayerwald Hackathon this weekend and continue working on the prototype. Most probably, we will have another update to share or an interactive demo set up after that. Stay tuned for our next update which will arrive very soon!

If you want to stay up-to-date, follow us on [LinkedIn](https://www.linkedin.com/company/compose-us/) and [Twitter / X](https://twitter.com/compose_us), watch this repository and [the Flottform implementation](https://github.com/compose-us/flottform). Feel free to reach out to us on any channel to send us feedback, ideas or links we need to check out. By the way, did we mention we’ve set up a [discussion board for this post](https://github.com/compose-us/build-in-public/discussions/3) already?

Cheers,

[![Tamara](../tamara.png)](https://www.linkedin.com/in/tamara-bogantseva/) and [![Jörn](../joern.png)](https://www.linkedin.com/in/joern-bernhardt/)
