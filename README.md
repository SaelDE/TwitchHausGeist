# TwitchHausGeist
This Twitch Bot offers two different usages. 

### Vote Bot

Checks every chat message for the following beginnings:

    +- / -+ / haugeNeut -> Neutral
    + / haugePlus -> Plus
    - / haugeMinu -> Minus

Posts an interim result every 20 seconds and an end result after 5 seconds of no additional votes.

Checks if more than 10 votes have been added before posting any result.


### Pipi Bot

Offers four commands to count the number of chat users who need to go to the toilet.

    !pipi -> To mention, that you need to go to the toilet
    !warpipi -> To mention, that you have been to the toilet before a break was announced
    !pipimeter -> Get the current count of users that need to go to toilet
    !pause -> Announce a break and reset the counter

### Installation

Clone this repository, create a venv and install dependencies using `pip` and the `requirements.txt`


### Configuration

Configuration of this bot is done by a `.env` file that is placed in the same directory 
as the `hausgeist.py` file. This file must look like this:

    # General
    IRC_TOKEN=<OAuth Token to be used for login. Can be generated by using https://twitchapps.com/tmi/>
    NICK=<Nick of the user the OAuth Token was generated for>
    CHANNEL=<Channel that should be entered>
    PREFIX=<Prefix for commands. In this case it is !>
    
    # Pipi Bot
    PIPI_DELAY=<Delay in seconds as spam protection. This is the number of seconds between two chat announcements>
    
    # Vote Bot
    VOTE_DELAY_END=<Number of seconds withoug a vote getting count. If this delay is reached, the vote is closed.>
    VOTE_DELAY_INTERIM=<Number of seconds between two announcements of the current vote count.>
    VOTE_MIN_VOTES=<Number of votes to be announced at all. A vote with less users votings will not be announced at all.>
