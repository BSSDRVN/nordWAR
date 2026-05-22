# nordWAR: a Local Baseball Analysis Project

WAR analysis plus extras for non-MLB townball leagues. The vast majority of these calculations come from FanGraphs, who have dutifully written down most of the math they work with to calculate fWAR. The bad news is that townball leagues frequently don't count as many statistics as the MLB does; frankly, we're lucky to be able to extrapolate as far as I do here. I'm also aware that "extrapolation" is a sin. Read on to find out how I've filled in the gaps.

If you are solely looking for the stats and output, [the PDF](https://github.com/BSSDRVN/nordWAR/blob/main/tcmabl.pdf) is what you're after. The bulk of the value for me is on page 5 (Two-League Babycake WARs), but if you are interested in league-by-league statistics for my baseball team, feel free to browse around.

## Disclaimer

This project is an independent, non-commercial tool designed to analyze publicly available baseball statistics from team websites hosted on HomeTeamsONLINE.com. The code included in this repository accesses only public-facing web pages and does not bypass any security measures.

Scraped data may be present in this repository. If you are a content owner of this data, reach out to me here on GitHub and I will take down what you wish. All data retrieval is for personal or educational use only, and I do not endorse usage of this data to identify individuals.

This project is not affiliated with, endorsed by, or sponsored by HomeTeamsONLINE.com or its partners. All trademarks, service marks, and content on the HomeTeamsONLINE website are the property of their respective owners.

## Some Explanations

It is true that some of this is vibes-based in lieu of formal fielding, catching, and framing stats. Note that this does not mean it is vibe-**coded**, it just means I've tuned this to where our league is. Take, for example, the calculation for fielding, $\text{Fielding} = (FPct - FPct_{\text{lg}})\cdot 0.8 \cdot G$, which scales fielding runs to 80% for seemingly no reason. It's already bad enough that we don't have much to go off of w/r/t fielders, so why do this here?

These leagues, the TCMABL and NMTBL, are volatile enough that an error (i.e. a lower fielding percentage) doesn't actually change the outcome of a game as much as it would in a league better at fielding, hence scaling down the expected amount of runs produced or lost by good or bad fielders. Offense just wins games more often, from what I've seen. (Also, lots of wins are error-laden.) Over the course of a full season, this still makes a difference; if you're a below average fielder, you are punished for making errors proportional to the amount of games you've played - and perhaps more importantly, you're still rewarded with nordWAR for being as close to 1.000 as possible, all the way down to the league average. 

A full explanation of the revised math is available [on this repo](https://github.com/BSSDRVN/nordWAR/blob/main/explanation.pdf); take it with a grain of salt since I wrote *that* with the help of an AI and have not yet fixed the formatting, so it may not cover every piece.

