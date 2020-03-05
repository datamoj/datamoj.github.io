---
layout: post
---
## Twitch Gambling Streamers

Imagine yourself sitting on a chair in front of a webcam, with some expensive geek figures and LED lightning in changing colors behind you, playing Blackjack with 2-3 thousand people in your stream and losing a ton of money every month in gambling. What you get in exchange is a couple hundred paid subscribers, some donations and some money from your sponsors. You continue playing and streaming for months, maybe even years, even though you don't make enough money from your channel to subsidize your gambling lose. You would probably not continue doing this, try to switch to video games streaming or just quit streaming and find a job. However, current streamers do not do that. They continue streaming even though some of them lose $50k/month.

Twitch is the biggest live streaming platform today with an average of 55 thousand live channels and 1.5 million viewers at any time. Twitch has 35.6k streaming partners and the number is growing very fast. Even though the platform is known by game streaming, this is about to change. "Just Chatting" category is the second most popular category after the popular MOBA game League of Legends. Today, another trend in Twitch is gambling streams. Experienced Blackjack and Poker players have huge number of followers and subscribers (who pay a monthly fee to support the streamer). 

Most Twitch streamers with more than a couple hundred subscribers stream for a living. They get paid from 2 to 3 dollars per each subscriber (depending on their channel's size and their agreement with Twitch). Twitch also shares a portion of the ad revenue with partner streamers. In addition to that, they usually have sponsors that giveaway their products or sometimes just give money to streamers to advertise their brand. 

### The Power of Influencers

Social media influencers have the power to affect the purchasing decisions of others because of his or her authority, knowledge, or position. For Twitch streamers, maybe the most important factor is the relationship with their audience. People subscribe to channels they like both to support them but also to be able to have more chance to connect them. Because of the relationship that streamers build with their audience, people like and trust their streamers. 

Nowadays, most Twitch streamers also have Youtube channels where they both create new content and also share their clips from their streams. Gambling streamers do that as well. In fact, it is even more helpful to them than others because in Youtube they have the chance to share only the clips that they win, instead of showing everything. We can't really blame them for this, because who wants to watch a man losing money for 30 minutes? (Maybe someone who wants to stop gambling?) However, it helps these people to build trust about their gambling techniques.

Some gambling Twitch streamers use this trust and authority to sell online courses to learn gambling techniques. Even though most people believe that these people make a living out of gambling, there are some pople questioning how these streamers can play hours and hours of Blackjack and Poker without going bankrupt. Some of them think that they play with fake money.

![A youtube comment thinking they are getting paid from the website](https://raw.githubusercontent.com/datamoj/datamoj.github.io/master/_posts/images/atalaypost1/figure2.png)
![Another youtube comment questioning streamer's winning](https://raw.githubusercontent.com/datamoj/datamoj.github.io/master/_posts/images/atalaypost1/figure3.png)


This is a very reasonable question, and you are about to learn the answer. Before starting to give you detailed explanations and graphs, there is something that needs to be cleared. This post is not designated to ruin people's businesses, authority or respect. I respect all business models as long as it is not legal, don't deceive people or steal money from people.

### The Analysis

Twitch streamers doesn't stream for minutes, they stream for hours. Therefore, it would be very tedious to watch someone's stream and note the balance of their account. To check if they actually make profit, I wrote a python script that converts Twitch Blackjack stream recordings to beautiful line charts. Here is an example before I explain what this means in detail:

![Line chart of a 20 minutes stream record from Twitch](https://raw.githubusercontent.com/datamoj/datamoj.github.io/master/_posts/images/atalaypost1/figure1.png)

What you see above is a line chart of the account balance from a 20-minutes BlackJack stream. As you can see that 20-minutes cost about $3000 for the streamer. Indeed, it is not always the case, sometimes they win and sometimes they lose. To see an overall performance, I applied the same technique to all streams within 2 weeks. I am putting the results to give you an idea. 

![Line chart of 2 weeks of streams from Twitch](https://raw.githubusercontent.com/datamoj/datamoj.github.io/master/_posts/images/atalaypost1/collage.png)

Looking at different figures in this collage, it is possible to see some wins and some loses. Sad part is that loses are more than wins, which brings a total loss of $22k in 2 weeks. One can say that 2 weeks is not enough to conclude that they lose money in the long run, therefore I am working on a larger project about this. 

### Conclusions

Because it is computationally expensive and it is hard to access Twitch streams, for now I limited this post only to two weeks of streams from one streamer. According to some  other tests and personal observations, I do think that this is mostly the case for all streamers. I believe the biggest question to ask here is that how do these streamers find enough money to continue their streams while they are not making that much money from their Twitch channel. Some first ideas that comes my mind are:

- They are getting paid a lot from their sponsors (websites).
- They make money from another business, they don't care about the cost.
- Sponsors give them some fake accounts with fake money, so that they can play without worrying about losing.
- My computations are wrong, they don't lose this much money.

These are hard ideas to prove because it is nearly impossible to know about the relationship between streamers and websites.

### Code

Code and all figures are available on Github.

All figures: [Github](https://github.com/datamoj/datamoj.github.io/tree/master/_posts/images/atalaypost1)

Code: [TwitchtoNumber](https://github.com/kutlay/twitchtonumber)


