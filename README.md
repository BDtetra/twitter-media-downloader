# twmd: CLI twitter media downloader (without api key)
forked from https://github.com/mmpx12/twitter-media-downloader

added -D --delay parameter (in seconds) between each fetch
added -c --cur cursor parameter for retaining cursor for resuming on error

## examples:
download vidoes from USER_NAME at directory D:\Downloads\twmd while checking 3000 posts, at a delay of 30 seconds per attempt
twmd -u USER_NAME -o "D:\Downloads\twmd" -v -n 3000 -D 30
same as above but for 10000 posts and using cursor mode, returning cursor position as log after each attempt
twmd -u USER_NAME -o "D:\Downloads\twmd" -v -n 10000 -D 30 -c "0"
use the returned cursor string to resume at point where you stopped last time
twmd -u USER_NAME -o "D:\Downloads\twmd" -v -n 10000 -D 30 -c "ALKJFSFDJ-_-5AFAFAFAFSDFKSJFLSFKJSAFAAAA"


## usage: 

```
Usage:
-h, --help                   Show this help
-u, --user=USERNAME          User you want to download
-t, --tweet=TWEET_ID         Single tweet to download
-n, --nbr=NBR                Number of tweets to download
-i, --img                    Download images only
-v, --video                  Download videos only
-a, --all                    Download images and videos
-r, --retweet                Download retweet too
-z, --url                    Print media url without download it
-R, --retweet-only           Download only retweet
-M, --mediatweet-only        Download only media tweet
-s, --size=SIZE              Choose size between small|normal|large (default
                             large)
-U, --update                 Download missing tweet only
-o, --output=DIR             Output directory
-f, --file-format=FORMAT     Formatted name for the downloaded file, {DATE}
                             {USERNAME} {NAME} {TITLE} {ID}
-d, --date-format=FORMAT     Apply custom date format.
                             (https://go.dev/src/time/format.go)
-L, --login                  Login (needed for NSFW tweets)
-C, --cookies                Use cookies for authentication
-p, --proxy=PROXY            Use proxy (proto://ip:port)
-V, --version                Print version and exit
-B, --no-banner              Don't print banner
-D, --delay                  (**NEW**)specify delay in seconds
-c, --cur                    (**NEW**)Use for specifying starting point
```
