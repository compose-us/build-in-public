# Hackathon Update

Hello y'all!

As promised, we have used the [Bayerwald Hackathon](https://www.bayerwald-hackathon.de/) to turn our prototype into something usable. Last time, we managed to open up a data channel between two devices, but we haven't actually sent a file. During the 24 hours, we managed to build a solid prototype that can actually send a file through the data channel and put it into a form field from one device to another.

## The hackathon experience

Before diving into the product again, let's appreciate the organization of the hackathon in Freyung. Usually, it's a great setting to play around with new technologies, work on side projects and meet interesting people.

This time, we had a new technology we wanted to check out ([WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)) and a product in mind that we wanted to push forward. Planning this up front helped us to get something demo-able out by the end of the event. Also, using technologies we already knew or worked with helped us to quickly create things: [SvelteKit](https://kit.svelte.dev/) as our backend and static server for the frontend, [the qrcode module](https://www.npmjs.com/package/qrcode) to show QR codes.

While taking breaks and chatting with people, we could gather more feedback. It's clear that many developers challenge the idea based on having created their own workarounds for this problem already. There was always a possible improvement to their workflow though: The amount of clicks, the maintenance or simply trying to get it from a device that does not have the workaround set up yet.

## What did we work on and how does it work?

To create a p2p connection, exchanging information between the peers up front is crucial. Interactive Connectivity Establishment (ICE) is used to check through which connection points the peers can communicate and an initial offer / answer is used to describe the actual session (SDP). This needs to be done through a so-called signaling channel.

Our first prototype used a manual process: We put the initial offer and ICE candidates into the hash part of a URL. We then had to send this to another device to open it and wait for it to generate an offer and ICE candidates. This reply had to be copied over again to the initial device and only then the peer connection could be opened. It wasn't an effective solution.

Basically, the exchange of offers and ICE candidates (the signaling)  should be simplified. We used our server to help with this: When the peer connected to the form says “create a p2p connection”, it sends a request to our server with its offer and initial ICE candidates. It receives a special URL to update its list of ICE candidates as this happens asynchronously. The other peer can connect to that URL by scanning a QR code that the first peer draws on its form. The peer receives the initial offer and ICE candidates from that URL and sends a reply to the server, making itself available for a connection. The initial peer currently polls for these replies and as soon as one is there, they can open a peer-to-peer data channel.

Ultimately, we created a script that identifies form file fields, adds an additional button to it, that allows the creation of the peer-to-peer connection. The file transfer into the form works!

![Video of us opening a form, go to URL from a secondary device, send something from there, see it appearing on the form on the first device and see the submit button working](./screencast.mp4)

## Additional challenges along the way

One challenge was sending files that are bigger than 16kb: Those files get split into multiple chunks and we need to glue them back together. In the prototype we do not have a real limitation about the size, but the initial peer may fail at some point due to memory restrictions.

Having a flaky internet connection at the hackathon resulted in ICE candidates not being populated at all. This made us think more about error states and how we need to handle them. While we didn't really dive deep into this topic yet, we now know that we need to invest more time into this topic. Devices could easily disconnect different networks.

Staying awake for 24 hours isn't really something that our bodies love. Whenever you're tired, it's probably better to rest than keep working on your project. After a night fueled by caffeine and a questionable amount of snacks, we managed to get the prototype styled and animated. The design decisions were born after a sleepless night of inspiration and you can tell it's not production ready yet. This experience underscores a valuable lesson: Hackathons are great at motivating us to quickly turn ideas into reality, but this can also lead to unintended consequences: In the rush to create, we often sacrifice rest, leading us down exciting yet potentially less optimal paths. It's a reminder that sometimes, the best solutions emerge when we're well-rested and thinking clearly. Stay tuned for the polished version coming soon. [Until then, check out the source we've used for the video above](https://github.com/compose-us/flottform/commit/407599bd43e93e6e35dd76bf939bfbd30718bbb0).

## Next steps

There are still some issues to be sorted out, like showing whether someone is connected instead of having the QR code open all the time, having a progress bar on the receiving end, cleaning up on the server after a while and debugging all the potential errors we could get.

One very important piece is missing though: Test users! We should be able to open up for test users pretty soon, so if you'd like to be one of our canaries, shoot us a message!

Many thanks to all the people who already reached out to us through DMs or discussed our project at meetups and the hackathon. We appreciate your engagement and we love to hear from you! Any comments, feedback, or ideas you'd like to share? Tell us on your favorite channel, or [join the conversation on our discussion board](https://github.com/compose-us/build-in-public/discussions/4). Follow us on [LinkedIn](https://www.linkedin.com/company/compose-us/), [Twitter / X](https://twitter.com/compose_us), and watch our repository and [the Flottform implementation](https://github.com/compose-us/flottform) to stay up-to-date with our project. Feel free to share this post with anyone who might be interested, and thank you for your support!

Cheers,

[![Tamara](../tamara.png)](https://www.linkedin.com/in/tamara-bogantseva/) and [![Jörn](../joern.png)](https://www.linkedin.com/in/joern-bernhardt/)
