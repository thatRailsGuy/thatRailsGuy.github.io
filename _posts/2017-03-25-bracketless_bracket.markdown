---
layout:     post
title:      "Bracketless Bracket"
subtitle:   "An alternative to picking all the winners in the NCAA Tournament"
date:       2017-03-25 22:00:00
author:     "Clint Cecil"
header-img: "img/basket-ball-header.jpg"
---

## The Game
A few years ago, we set out upon looking for ways to choose our draft order for fantasy football and I stumbled on an article about an alternative betting pool that didn't require much prior knowledge to win. I can't find the original source of the article (if you know it, please send it to me.)

The gist of the game is that every participant picks one team from each seed. That is one 1 seed, one 2 seed, one 3 seed, etc. Each win that team earns earns the participant points. Points are based on seed, starting with 100 points for a 1 seed, 110 for a 2 seed, all the way down to 250 for a 16 seed win.

The first year doing it, we each threw in $10 and also used it to pick our fantasy football draft order to huge success. The biggest worry was that we would have ties and have to settle the draft order some other way, but with fourteen participants, we had no ties.

After the first year of success, we continued the following year without the involvement of the fantasy football league. Again, we had fourteen participants, and this time we had one tie for seventh place. In both of the first years it came down to the final game for the win.

This year, with half the elite eight games complete, I think the winner has been determined. I haven't run all the numbers, but from a cursory glance it would seem the leader is uncatchable with the lineups of the other participants. Personally, I would have finished last if it weren't for my Dad performing even worse than I did.

This year we expanded to have 19 teams competing. We have one tie currently, but the players have opposing teams facing off in the next round to break the tie. I will update once the bracket is complete with final results.

I would like to invite more people, but I fear that if too many people join there will be more issues of ties in the game. This may end being an interesting statistical problem to determine maximum number of participants without the likelihood of a tie for the top few spots.

While there are 2^32 sets of teams possible to choose, many of the choices end up being equivalent from a score perspective. For instance, this year, no 13, 14, 15, or 16 seed won a game. With all the ties at different seed levels there were essentially 46,656 unique scores of the original 4,294,967,296 lineups (as of 3/25 with 5 games left). This isn't eliminating ways you can tie with different lineups, just eliminates differences when multiple teams of the same seed scored the same number of wins.

## The Logistics and Tech Behind the Game

For the first year I had participants email me their choices for each seed and I made a complicated spreadsheet to keep track of all the scoring. Being lazy last year led me to reuse the same sheet. Everybody could view it on google spreadsheets and check the scores and I updated it daily with the results.

This year I built a quick rails app on Selection Sunday with a simple form to select each seed and threw it up on digital ocean. With the exception of some problems from a few technologically hindered people, the form and app worked without a hitch.

For some analysis, I added pages which calculate the optimal lineup possible and which show how many people selected each team and how teams of each seed compare.

While simple, the app does a lot of calculations on the fly that I may run as a one time calculation on scoring updates and serve as static data in the future.

I would also like to make a better interface for selecting teams, maybe something that highlights all the paths through the bracket there are for teams participants already selected so they don't end up picking teams that face each other in the first couple rounds. That would require a bit more logic in terms of the bracket structure. Currently there are team records with seeds, a boolean to show if they're eliminated, and win count.

The other improvement would be an admin interface. I logged into the server and used the console to update each team's records with win counts and elimination status this year.

I'm hoping to open source the code and share it around to some other sports fans to see if anybody else likes the format for next year. This might also lead to some interesting pull requests to add features to the site.


***
Header courtesy of [http://www.freewebheaders.com](http://www.freewebheaders.com)
