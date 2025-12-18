
This project aims to explore how track popularity is distributed across the catalogues of jazz and classical artists. 
If we can understand the patterns that differentiate consistent artists from those whose streaming activity is driven by a small number of breakout tracks, and if we can see how these patterns manifest differently across genres, we can potentially glean crucial signals from scarce and noisy early artist data.

First, a quick summary of the more technical explanation below:

I used a standard inequality metric, the Gini Coefficient, to measure how unequally popular the top 10 tracks of some artists are.
The average Gini was very similar for jazz and classical musicians, with classical showing a greater spread. But we have too few datapoints in this sketch analysis to make any conclusions about sweeping patterns. 
We should consider several improvements: a sampling method to choose thousands of datapoints in a representative way; an analysis of genre boundaries/definitions to make meaningful conclusions; a more detailed inequality analysis that improves on the Gini coefficient.

In more detail:

We used publicly available data from spotify's API, focusing on spotify's "popularity" metric, a proprietary measure of recent activity on a 0-100 scale, with songs ranked nearer 100 showing a greater number of recent interactions on the platform.
It is important to note the limitations of this measure. It considers neither the full track listing nor most of the past activity of an artist. It is popularity, but only right now. Unfortunately, Spotify's API doesn't provide a true alternative, so we should like to look at other sources, like Chartmetric, kworb, etc. Perhaps, in extreme cases, we might consider scraping methods to get data.

In addition, we limited our analysis to the top 10 tracks from each artist, which, naturally, do not have to come from the same album. This means that what we measure as "equal" popularity, may point to a consistency of hits across albums, rather than a consistency of albums with equally-liked songs.

Note also that we curated artists manually, and our choices of genre assignment affect our ability to notice patterns - there is some more careful boundary-drawing to be done here, likely depending on current definitions of genres or indeed the genres that artists are currently working within (since the popularity metric prioritises recent activity).

To measure the inequality of track popularity, we use the Gini Coefficient, often used in economics. The Gini Coefficient of a dataset is a number between 0 and 1, which, if closer to 0, represents more equally-distributed data, and if closer to 1, more diverse data.

When plotted on a bar chart, the data revealed overwhelmingly low Gini coefficients, meaning that most of our artists get even engagement on Spotify on their top 10 songs. An interesting outlier was Jeff Goldblum, with a Gini of 0.492754, far above the Jazz average of 0.078812. It is not surprising that in the music of a celebrity mainly known as an actor, certain tracks are disproportionally exposed to his full fanbase's attention.

Box plots of the data show little difference in the average Gini, but do reveal a greater spread in the coefficients of classical musicians. 
We should look at the distribution curves in more detail for each artist, because Gini alone isn't showing the differences one might expect to see between classical and Jazz audience engagement. Naturally, there could simply be little difference, but it would take more investigation to establish that. 


Repository comments:

See "notebooks" folder for the commented code in a Jupyter Notebook.
See "data" folder for graphs and tables of data only.

