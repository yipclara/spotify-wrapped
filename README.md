# spotify-wrapped

## Why
Do you feel like every year, Spotify Wrapped gets worse and less insteresting? Wish you could get your actual stats from the whole calendar year (rip december)? Then congrats today's your day!!

## How 
1. Request all your Spotify account streaming data [here](https://www.spotify.com/us/account/privacy/)
   1. It may take a few days
   2. Spotify will only send you the past 365 days
   3. There are 2 ways to get your full calendar year:
      1. Request your data twice, once in Dec and again in Jan. Then slice the datasets together
      2. Request your extended history (this is everything you've ever listened to) and trim down to the year of interest. This notebook assumes you went with option 1 -- if option 2, your dataset will look a little different and you can skip the api call to lookup the artistIds
1. Concat the `StreamingHistory_music_{id}` json files. Each file with contain an array of songs, concat into a single continuous array
2. Setup a Spotify dev account and create an app to get credentials to the Spotify api [docs](https://developer.spotify.com/documentation/web-api)
3. Setup an environment to run a jupyter notebook (I used google colab)
4. Run the `spotify_2024.ipynb` notebook
   1. Add your streaming history json
   2. Everything up until the `genre` section should be plug and play
1. Profit aka make a sick ppt to show your friends

### Genre 
Spotify doesn't tag genres at the song-level, so the best we can do is pull the artist genres (these are also arrays of variable length, including empty). There's a cell in the notebook that dedupes all your genres and saves them to a csv so you can tag them manually. Tbh its tedious and I wish I knew a better approach, but my hope is since I did it for 2024, most of these tags will be applicable for my listening history next year! 

I bucketed all my genre tags into a handful of themes, by no means do I expect anyone else to agree with how I decided to label things. Feel free to make your own! At the end of the day, the genre visualization is only as interesting and meaningful as you choose to make it!
