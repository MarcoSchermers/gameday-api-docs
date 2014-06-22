# miniscoreboard.xml

The miniscoreboard.xml file provides basic scoreboard information. It consists of the following elements:

+ [`<game>`](#egame)
+ [`game_status>`](#egamestatus)
+ [`<linescore>`](#elinescore)
+ [`<inning>`](#einning)
+ [`<r>`](#elruns)
+ [`<h>`](#elhits)
+ [`<e>`](#elerrors)
+ [`<hr>`](#elhomeruns)
+ [`<sb>`](#elstolenbases)
+ [`<so>`](#elstrikeouts)
+ [`<post_game>`](#epostgame)
+ [`<winning_pitcher>`](#ewinningpitcher)
+ [`<losing_pitcher>`](#elosingpitcher)
+ [`save_pitcher>`](#esavepitcher)
+ [`<home_team>`](#ehometeam)
+ [`<away_team>`](#eawayteam)
+ [`<home_runs>`](#ehomeruns)
+ [`<player>`](#eplayer)
+ [`<in_game>`](#eingame)
+ [`<batter>`](#ebatter)
+ [`<pitcher>`](#epitcher)
+ [`<opposing_pitcher>`](#eopposingpitcher)
+ [`<ondeck>`](#eondeck)
+ [`<inhole>`](#einhole)
+ [`<runner_on_1b>`](#erunneronfirst)
+ [`<runner_on_2b>`](#erunneronsecond)
+ [`<runner_on_3b>`](#erunneronthird)
+ [`<review>`](#ereview)

These elements form the following structure:

    <game>
        <game_status/>
        <linescore>
            <inning/>
            <r/>
            <h/>
            <e/>
            <hr/>
            <sb/>
            <so/>
        </linescore>
        <post_game>
            <winning_pitcher/>
            <losing_pitcher/>
            <save_pitcher/>
            <away_team/>
            <home_team/>
        </post_game>
        <home_runs> # only present if one or more players hit a Home Run
            <player/>
        </home_runs>
        <in_game> # only present if game postponed
            <batter/>
            <pitcher/>
            <opposing_pitcher/>
            <ondeck/>
            <inhole/>
            <runner_on_1b/>
            <runner_on_2b/>
            <runner_on_3b/>
        </in_game>
        <review/> # only present if game is from 2011/2012 playoffs OR 2013-present

## <a name="egame">Game Element</a>

The `<game>` element describes basic game information.

    <game id="2011/07/09/tbamlb-nyamlb-1" home_name_abbrev="NYY" away_name_abbrev="TB" home_code="nya" away_code="tba" home_file_code="nyy" away_file_code="tb" home_team_id="147" away_team_id="139" home_games_back="-" away_games_back="6.0" home_games_back_wildcard="" away_games_back_wildcard="-" venue_w_chan_loc="USNY0172" gameday_sw="P" double_header_sw="N" gameday="2011_07_09_tbamlb_nyamlb_1" home_win="52" home_loss="35" away_win="49" away_loss="40">

### Game Attributes

+ [ID](#gid)
+ [Venue Weather Channel Code](#gvenueweatherchannelcode)
+ [Gameday](#ggameday)
+ [Gameday Streaming Web](#ggamedaystreamingweb)
+ [Double Header Streaming Web](#gdoubleheaderstreamingweb)
+ [Away Team ID](#gawayid)
+ [Away Team Code](#gawaycode)
+ [Away Team File Code](#gawayfilecode)
+ [Away Team Abbreviation](#gawayabbreviation)
+ [Away Team Wins](#gawaywins)
+ [Away Team Losses](#gawaylosses)
+ [Away Team Games Back](#gawaygamesback)
+ [Away Team Games Back Wild Card](#gawaygamesbackwildcard)
+ [Home Team ID](#ghomeid)
+ [Home Team Code](#ghomecode)
+ [Home Team File Code](#ghomefilecode)
+ [Home Team Abbreviation](#ghomeabbreviation)
+ [Home Team Wins](#ghomewins)
+ [Home Team Losses](#ghomelosses)
+ [Home Team Games Back](#ghomegamesback)
+ [Home Team Games Back Wild Card](#ghomegamesbackwildcard)

#### <a name="gid">ID</a>

`id` is a unique identifier for the game. It has the same value as the the `id` attribute from the `<game>` element in the linescore.xml file.

#### <a name="gvenueweatherchannelcode">Venue Weather Channel Code</a>

`venue_w_chan_loc` is the Weather Channel location code. The value takes the format `USABXXXX` where `AB` is the two letter state abbreviation and `XXXX` is a four digit code, such that the Bronx, NY code is `USNY0172`. This code is used by [AOL Weather](http://weather.aol.com/), [The Weather Channel](http://www.weather.com/), and [Yahoo! Weather](https://weather.yahoo.com/). To view all United States weather location codes take a look [here](https://www.edg3.co.uk/snippets/weather-location-codes/united-states-of-america/).

#### <a name="ggameday">Gameday</a>

`gameday` is the gameday ID component of the game URL.

#### <a name="ggamedaystreamingweb">Gameday Streaming Web</a>

`gameday_sw` identifies if the game is available for streaming on the web. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes
+ `E` -- Unknown
+ `P` -- Paid

#### <a name="gdoubleheaderstreamingweb">Double Header Streaming Web</a>

`double_header_sw` identifies if the double header is available for streaming on the web. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes
+ `S` -- Subscription

#### <a name="gawayid">Away Team ID</a>

`away_team_id` is the ID number used for the away team.

#### <a name="gawaycode">Away Team Code</a>

`away_code` is the three-letter identifer used for the away team. See all team codes [here](./team-information).

#### <a name="gawayfilecode">Away Team File Code</a>

`away_file_code` is [presumably] used to organize the away team's Gameday files.

#### <a name="gawayabbreviation">Away Team Abbreviation</a>

`away_name_abbrev` is the away team's abbreviation. See all team abbreviations [here](./team-information).

#### <a name="gawaywins">Away Team Wins</a>

`away_win` is the total away team wins, including the game in question.

#### <a name="gawaylosses">Away Team Losses</a>

`away_loss` is the total away team losses, including the game in question.

#### <a name="gawaygamesback">Away Team Games Back</a>

`away_games_back` is the total number of games back for the away team. If the away team is leading the division, the value is `-`.

#### <a name="gawaygamesbackwildcard">Away Team Games Back Wild Card</a>

`away_games_back_wildcard` is the total number of games back in the wild card for the away team. This may not be present. If the away team is leading the wild card, the value is `-`.

#### <a name="ghomeid">Home Team ID</a>

`home_team_id` is the ID number used for the home team.

#### <a name="ghomecode">Home Team Code</a>

`home_code` is the three-letter identifer used for the home team. See all team codes [here](./team-information).

#### <a name="ghomefilecode">Home Team File Code</a>

`home_file_code` is [presumably] used to organize the home team's Gameday files.

#### <a name="ghomeabbreviation">Home Team Abbreviation</a>

`home_name_abbrev` is the home team's abbreviation. See all team abbreviations [here](./team-information).

#### <a name="ghomewins">Home Team Wins</a>

`home_win` is the total home team wins, including the game in question.

#### <a name="ghomelosses">Home Team Losses</a>

`home_loss` is the total home team losses, including the game in question.

#### <a name="ghomegamesback">Home Team Games Back</a>

`home_games_back` is the total number of games back for the home team. If the home team is leading the division, the value is `-`.

#### <a name="ghomegamesbackwildcard">Home Team Games Back Wild Card</a>

`home_games_back_wildcard` is the total number of games back in the wild card for the home team. This may not be present. If the home team is leading the wild card, the value is `-`.

## <a name="#egamestatus">Game Status Element</a>

The `<game_status/>` element describes the game's status.

### Game Status Attributes

+ [Status](#gsstatus)
+ [Status Indicator](#gsindicator)
+ [Inning](#gsinning)
+ [Top of Inning](#gstopofinning)
+ [Inning State](#gsinningstate)
+ [Balls](#gsballs)
+ [Strikes](#gsstrikes)
+ [Outs](#gsouts)
+ [Delay Reason](#gsdelayreason)

#### <a name="gsstatus">Status</a>

`status` identifies the game status. It has the following values:

+ `Final`
+ `Completed Early`
+ `Postponed`
+ `Game Over`

#### <a name="gsindicator">Status Indicator</a>

`status_ind` identifies the game status as an abbreviation. It has one of the following values:

+ `F` -- Final
+ `FT` -- Final and score tied
+ `FR` -- Final and called due to rain
+ `DR` -- Delayed due to rain
+ `DS` -- Delayed due to snow
+ `DO` -- (Delayed Other?)
+ `FO` -- Final (completed early, reason: Other)
+ `O` -- (Other?)

#### <a name="gsinning">Inning</a>

`inning` is the number of innings played.

#### <a name="gstopofinning">Top of Inning</a>

`top_inning` identifies if the game concluded in the top of the last scheduled inning. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes

#### <a name="gsinningstate">Inning State</a>

`inning_state` is a text description of the inning when the game concluded. It appears that this value is an empty string.

#### <a name="gsballs">Balls</a>

`b` is the number of balls at the end of the game. It has one of the following values:

+ `0`
+ `1`
+ `2`
+ `3`

#### <a name="gsstrikes">Strikes</a>

`s` is the number of strikes at the end of the game. It has one of the following values:

+ `0`
+ `1`
+ `2`

#### <a name="gsouts">Outs</a>

`o` is the number of outs in the last inning. It has one of the following values:

+ `0`
+ `1`
+ `2`
+ `3`

#### <a name="gsdelayreason">Delay Reason</a>

`delay_reason` is the reason for game stoppage. If present, it has one of the following values:

+ `Tied`
+ `Rain`
+ `Snow`
+ `Other`
+ `""` -- Empty string value


## <a name="elinescore">Linescore Element</a>

The `<linescore>` element is a container element that does not have any attributes.

## <a name="einning">Inning Element</a>

The `<inning/>` element describes a single inning of scoring. If the home does not need to bat in the bottom of an inning. The `home` attribute will not be present.

    <inning away="0" home="2"/>

+ [Away Team Runs](#iaway)
+ [Home Team Runs](#ihome)

#### <a name="iaway">Away Team</a>

`away` is the number of runs scored by the away team.

#### <a name="ihome">Home Team</a>

`home` is the number runs scored by the home team.

## <a name="elruns">Run Element</a>

The `<r/>` element describes the total runs scored by each team and includes a differential.

    <r away="4" home="5" diff="1"/>

### Run Attributes

+ [Away Team Runs](#raway)
+ [Home Team Runs](#rhome)
+ [Differential](#rdiff)

#### <a name="raway">Away Team Runs</a>

`away` is the total number of runs scored by the away team.

#### <a name="rhome">Home Team Runs</a>

`home` is the total number of runs scored by the home team.

#### <a name="rdiff">Differential</a>

`diff` is the differential between the team run totals.

## <a name="elhits">Hit Element</a>

The `<h/>` element describes the number of hits for each team.

    <h away="5" home="10"/>

### Hit Attributes

+ [Away Team Hits](#haway)
+ [Home Team Hits](#hhome)

#### <a name="haway">Away Team Hits</a>

`away` is the total number of hits by the away team.

#### <a name="hhome">Home Team Hits</a>

`home` is the total number of hits by the home team.

## <a name="elerrors">Error Element</a>

The `<e/>` element describes the number of errors for each team.

    <e away="0" home="0"/>

### Error Attributes

+ [Away Team Errors](#eraway)
+ [Home Team Errors](#erhome)

#### <a name="eraway">Away Team Errors</a>

`away` is the total number of errors by the away team.

#### <a name="erhome">Home Team Errors</a>

`home` is the total number of errors by the home team.

## <a name="elhomeruns">Home Run Element</a>

The `<hr/>` element describes the number of home runs for each team.

    <hr away="2" home="1"/>

### Home Run Attributes

+ [Away Team Home Runs](#hraway)
+ [Home Team Home Runs](#hrhome)

#### <a name="hraway">Away Team Home Runs</a>

`away` is the total number of home runs by the away team.

#### <a name="hrhome">Home Team Home Runs</a>

`home` is the total number of home runs by the home team.

## <a name="elstolenbases">Stolen Base Element</a>

The `<sb/>` element describes the number of stolen bases for each team.

    <sb away="4" home="2"/>

### Stolen Base Attributes

+ [Away Team Stolen Bases](#sbaway)
+ [Home Team Stolen Bases](#sbhome)

#### <a name="sbaway">Away Team Stolen Bases</a>

`away` is the total number of stolen bases by the away team.

#### <a name="sbhome">Home Team Stolen Bases</a>

`home` is the total number of stolen bases by the home team.

## <a name="elstrikeouts">Strike Out Element</a>

The `<so/>` element describes the number of strikes for each team.

    <so away="5" home="13"/>

### Strike Out Attributes

+ [Away Team Strike Outs](#soaway)
+ [Home Team Strike Outs](#sohome)

#### <a name="soaway">Away Team Strike Outs</a>

`away` is the total number of strike outs by the away team.

#### <a name="sohome">Home Team Strike Outs</a>

`home` is the total number of strike outs by the home team.

## <a name="epostgame">Post Game Element</a>

The `<post_game>` element describes game information.

    <post_game venue="Yankee Stadium" date="July 9, 2011">

### Post Game Attributes

+ [Date](#pgdate)
+ [Venue](#pgvenue)

#### <a name="pgdate">Date</a>

`date` is the date of the game.

#### <a name="pgvenue">Venue</a>

`venue` is the venue's name.

## <a name="ewinningpitcher">Winning Pitcher Element</a>

The `<winning_pitcher/>` element describes the winning pitcher.

    <winning_pitcher id="502085" ip="1.0" er="1" era="1.27" wins="2" losses="0" number="30" last="Robertson" first="David" name_display_roster="Robertson, D"/>

### Winning Pitcher Attributes

+ [ID](#wpid)
+ [First](#wpfirst)
+ [Last](#wplast)
+ [Display Name](#wpdisplayname)
+ [Number](#wpnumber)
+ [Innings wptched](#wpinningswptched)
+ [Earned Runs](#wpearnedruns)
+ [Wins](#wpwins)
+ [Losses](#wplosses)
+ [ERA](#wpera)

#### <a name="wpid">ID</a>

`id` is the ID number used for the player.

#### <a name="wpfirst">First</a>

`first` is the player's first name.

#### <a name="wplast">Last</a>

`last` is the player's last name.

#### <a name="wpdisplayname">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="wpnumber">Number</a>

`number` is the player's number.

#### <a name="wpinningswptched">Innings wptched</a>

`ip` is the total number of innings wptched by the player.

#### <a name="wpearnedruns">Earned Runs</a>

`er` is the total number of earned runs allowed by the player.

#### <a name="wpwins">Wins</a>

`wins` is the total number of wins by the player, season to date.

#### <a name="wplosses">Losses</a>

`losses` is the total number of losses by the player, season to date.

#### <a name="wpera">ERA</a>

`era` is the player's ERA, season to date.

## <a name="elosingpitcher">Losing Pitcher Element</a>

The `<losing_pitcher/>` element describes the losing pitcher.

    <losing_pitcher id="407908" ip="1.1" er="1" era="3.73" wins="2" losses="4" number="62" last="Peralta" first="Joel" name_display_roster="Peralta, Jo"/>

### Losing Pitcher Attributes

+ [ID](#lpid)
+ [First](#lpfirst)
+ [Last](#lplast)
+ [Display Name](#lpdisplayname)
+ [Number](#lpnumber)
+ [Innings lptched](#lpinningslptched)
+ [Earned Runs](#lpearnedruns)
+ [Wins](#lpwins)
+ [Losses](#lplosses)
+ [ERA](#lpera)

#### <a name="lpid">ID</a>

`id` is the ID number used for the player.

#### <a name="lpfirst">First</a>

`first` is the player's first name.

#### <a name="lplast">Last</a>

`last` is the player's last name.

#### <a name="lpdisplayname">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="lpnumber">Number</a>

`number` is the player's number.

#### <a name="lpinningslptched">Innings lptched</a>

`ip` is the total number of innings lptched by the player.

#### <a name="lpearnedruns">Earned Runs</a>

`er` is the total number of earned runs allowed by the player.

#### <a name="lpwins">Wins</a>

`wins` is the total number of wins by the player, season to date.

#### <a name="lplosses">Losses</a>

`losses` is the total number of losses by the player, season to date.

#### <a name="lpera">ERA</a>

`era` is the player's ERA, season to date.

## <a name="esavepitcher">Saving Pitcher Element</a>

The `<save_pitcher/>` element describes the saving pitcher. If a save was not recorded, this element will not be present.

    <save_pitcher id="121250" ip="1.0" er="0" era="1.85" wins="1" losses="1" saves="22" svo="26" number="42" last="Rivera" first="Mariano" name_display_roster="Rivera"/>

### Saving Pitcher Attributes

+ [ID](#spid)
+ [First](#spfirst)
+ [Last](#splast)
+ [Display Name](#spdisplayname)
+ [Number](#spnumber)
+ [Innings sptched](#spinningssptched)
+ [Earned Runs](#spearnedruns)
+ [Wins](#spwins)
+ [Losses](#splosses)
+ [Saves](#spsaves)
+ [Save Opportunities](#spsaveopportunities)
+ [ERA](#spera)

#### <a name="spid">ID</a>

`id` is the ID number used for the player.

#### <a name="spfirst">First</a>

`first` is the player's first name.

#### <a name="splast">Last</a>

`last` is the player's last name.

#### <a name="spdisplayname">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="spnumber">Number</a>

`number` is the player's number.

#### <a name="spinningssptched">Innings sptched</a>

`ip` is the total number of innings sptched by the player.

#### <a name="spearnedruns">Earned Runs</a>

`er` is the total number of earned runs allowed by the player.

#### <a name="spwins">Wins</a>

`wins` is the total number of wins by the player, season to date.

#### <a name="splosses">Losses</a>

`losses` is the total number of losses by the player, season to date.

#### <a name="spsaves">Saves</a>

`saves` is the total number of saves by the player, season to date.

#### <a name="spsaveopportunities">Save Opportunities</a>

`svo` is the total number of save opportunities by the player, season to date.

#### <a name="spera">ERA</a>

`era` is the player's ERA, season to date.

## <a name="ehometeam">Home Team Element</a>

The `<home_team/>` element describes the home team's record.

    <home_team wins="52" losses="35"/>

### Home Team Attributes

+ [Wins](#hwins)
+ [Losses](#hlosses)

#### <a name="hwins">Wins</a>

`wins` is the total number of wins, season to date.

#### <a name="hlosses">Losses</a>

`losses` is the total number of losses, season to date

## <a name="eawayteam">Away Team Element</a>

The `<away_team/>` element describes the away team's record.

    <away_team wins="49" losses="40"/>

### Away Team Attributes

+ [Wins](#awins)
+ [Losses](#alosses)

#### <a name="awins">Wins</a>

`wins` is the total number of wins, season to date.

#### <a name="alosses">Losses</a>

`losses` is the total number of losses, season to date

## <a name="ehomeruns">Home Runs Element</a>

The `<home_runs>` element is a container element that does not have any attributes.

## <a name="eplayer">Player Element</a>

The `<player/>` element describes a player who has hit a home run.

    <player id="116539" team_code="nya" hr="1" std_hr="3" inning="3" runners="0" number="2" last="Jeter" first="Derek" name_display_roster="Jeter"/>

### Player Attributes

+ [ID](#plid)
+ [First](#plfirst)
+ [Last](#pllast)
+ [Display Name](#pldisplayname)
+ [Number](#plnumber)
+ [Team Code](#plteamcode)
+ [Inning](#plinning)
+ [Home Run Number](#plhomerunnumber)
+ [Runners On Count](#plrunnersoncount)
+ [Season To Date Home Runs](#plseasontodatehomeruns)

#### <a name="plid">ID</a>

`id` is the ID number used for the player.

#### <a name="plfirst">First</a>

`first` is the player's first name.

#### <a name="pllast">Last</a>

`last` is the player's last name.

#### <a name="pldisplayname">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="plnumber">Number</a>

`number` is the player's number.

#### <a name="plteamcode">Team Code</a>

`team_code` is the player's team code. See all team codes [here](./team-information).

#### <a name="plinning">Inning</a>

`inning` is the inning number when the home run was hit.

#### <a name="plhomerunnumber">Home Run Number</a>

`hr` is the total number of home runs hit by the player in the game, including the current home run.

#### <a name="plrunnersoncount">Runners On Count</a>

`runners` is the total number of runners on base. It has one of the following values:

+ `0`
+ `1`
+ `2`
+ `3`

#### <a name="plseasontodatehomeruns">Season To Date Home Runs</a>

`std_hr` is the total number of home runs by the player, season to date.

## <a name="eingame">In Game Element</a>

The `<in_game>` element describes game information for a game that has been postponed. It will not be present if the game is official.

    <in_game last_pbp="Shelley Duncan flies out to left fielder Carlos Peguero. ">

### In Game Attributes

+ [Last Play By Play](#igpbp)
+ [Time Code](#igtimecode)

#### <a name="igpbp">Last Play By Play</a>

`last_pbp` is a description of the last play before the game was postponed.

#### <a name="igtimecode">Time Code</a>

`timecode` identifies when the game was stopped. If the value is not an empty string, it takes the format `YYYYMMDD_HHMMSS`.

## <a name="epitcher">Pitcher Element</a>

The `<batter/>` element describes the player at bat when the game was stopped. It is only present if the `<in_game>` element is also present.

    <batter id="400098" pos="DH" ab="0" hit="0" avg=".340" hr="5" rbi="16" slg=".528" obp=".403" ops=".932" number="48" last="Hafner" first="Travis" name_display_roster="Hafner"/>

### Batter Attributes

+ [ID](#baid)
+ [First](#bafirst)
+ [Last](#balast)
+ [Display Name](#banamedisplay)
+ [Number](#banumber)
+ [Position](#baposition)
+ [At Bats](#baatbats)
+ [Hits](#bahits)
+ [Batting Average](#babattingaverage)
+ [Home Runs](#bahomeruns)
+ [RBI](#barbi)
+ [Slugging Percentage](#basluggingpercentage)
+ [On-base Percentage](#baonbasepercentage)
+ [On-base + Slugging Percentage](#baonbaseplussluggingpercentage)

#### <a name="baid">ID</a>

`id` is the ID number used for the player.

#### <a name="bafirst">First</a>

`first` is the player's first name.

#### <a name="balast">Last</a>

`last` is the player's last name.

#### <a name="banamedisplay">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="banumber">Number</a>

`number` is the player's number.

#### <a name="baposition">Position</a>

`pos` is the player's position. It has one of the following values:

+ `C` -- Catcher
+ `1B` -- First Base
+ `2B` -- Second Base
+ `3B` -- Third Base
+ `SS` -- Shortstop
+ `LF` -- Left Field
+ `CF` -- Center Field
+ `RF` -- Right Field
+ `DH` -- Designated Hitter

#### <a name="baatbats">At Bats</a>

`ab` is the total number of at bats for the player in the game.

#### <a name="bahits">Hits</a>

`hit` is the total number of hits for the player in the game.

#### <a name="babattingaverage">Batting Average</a>

`avg` is the player's batting average, season to date.

#### <a name="bahomeruns">Home Runs</a>

`hr` is the total number of home runs for the player, season to date.

#### <a name="barbi">RBI</a>

`rbi` is the total number of RBI for the player, season to date.

#### <a name="basluggingpercentage">Slugging Percentage</a>

`slg` is the player's slugging percentage, season to date.

#### <a name="baonbasepercentage">On-base Percentage</a>

`obp` is the player's on-base percentage, season to date.

#### <a name="baonbaseplussluggingpercentage">On-base + Slugging Percentage</a>

`ops` is the player's on-base plus slugging percentage, season to date.

## <a name="epitcher">Pitcher Element</a>

The `<pitcher/>` element describes the player on the mound when the game was stopped. It is only present if the `<in_game>` element is also present.

    <pitcher id="407853" ip="0.2" er="0" era="4.70" wins="1" losses="4" number="45" last="Bedard" first="Erik" name_display_roster="Bedard"/>

### Pitcher Attribtues

+ [ID](#piid)
+ [First](#pifirst)
+ [Last](#pilast)
+ [Display Name](#pinamedisplay)
+ [Number](#pinumber)
+ [Innings Pitched](#piinningspitched)
+ [Earned Runs](#piearnedruns)
+ [Wins](#piwins)
+ [Losses](#pilosses)
+ [ERA](#piera)

#### <a name="piid">ID</a>

`id` is the ID number used for the player.

#### <a name="pifirst">First</a>

`first` is the player's first name.

#### <a name="pilast">Last</a>

`last` is the player's last name.

#### <a name="pinamedisplay">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="pinumber">Number</a>

`number` is the player's number.

#### <a name="piinningspitched">Innings Pitched</a>

`ip` is the total number of innings pitched by the player in the game.

#### <a name="piearnedruns">Earned Runs</a>

`er` is the total number of earned runs allowed by the player in the game.

#### <a name="piwins">Wins</a>

`wins` is the total number of wins by the player, season to date.

#### <a name="pilosses">Losses</a>

`losses` is the total number of losses by the player, season to date.

#### <a name="piera">ERA</a>

`era` is the player's ERA, season to date.

## <a name="eopposingpitcher">Opposing Pitcher Element</a>

The `<opposing_pitcher/>` element describes the pitcher whose team is at bat when the game was stopped. It is only present if the `<in_game>` element is also present.

    <opposing_pitcher id="502229" ip="1.0" er="0" era="3.46" wins="1" losses="0" number="32" last="White" first="Alex" name_display_roster="White"/>

### Opposing pitcher Attribtues

+ [ID](#opid)
+ [First](#opfirst)
+ [Last](#oplast)
+ [Display Name](#opnamedisplay)
+ [Number](#opnumber)
+ [Innings optched](#opinningsoptched)
+ [Earned Runs](#opearnedruns)
+ [Wins](#opwins)
+ [Losses](#oplosses)
+ [ERA](#opera)

#### <a name="opid">ID</a>

`id` is the ID number used for the player.

#### <a name="opfirst">First</a>

`first` is the player's first name.

#### <a name="oplast">Last</a>

`last` is the player's last name.

#### <a name="opnamedisplay">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="opnumber">Number</a>

`number` is the player's number.

#### <a name="opinningsoptched">Innings optched</a>

`ip` is the total number of innings optched by the player in the game.

#### <a name="opearnedruns">Earned Runs</a>

`er` is the total number of earned runs allowed by the player in the game.

#### <a name="opwins">Wins</a>

`wins` is the total number of wins by the player, season to date.

#### <a name="oplosses">Losses</a>

`losses` is the total number of losses by the player, season to date.

#### <a name="opera">ERA</a>

`era` is the player's ERA, season to date.

## <a name="eondeck">On Deck Element</a>

The `on_deck` element describes the batter on deck when the game was stopped. It is only present if the `<in_game>` element is also present.

    <ondeck id="111851" pos="2B" ab="0" hit="0" avg=".273" hr="2" rbi="21" slg=".360" obp=".295" ops=".654" number="20" last="Cabrera" first="Orlando" name_display_roster="Cabrera, O"/>

### On Deck Attributes

+ [ID](#odid)
+ [First](#odfirst)
+ [Last](#odlast)
+ [Display Name](#odnamedisplay)
+ [Number](#odnumber)
+ [Position](#odposition)
+ [At Bats](#odatbats)
+ [Hits](#odhits)
+ [Batting Average](#odbattingaverage)
+ [Home Runs](#odhomeruns)
+ [RBI](#odrbi)
+ [Slugging Percentage](#odsluggingpercentage)
+ [On-base Percentage](#odonbasepercentage)
+ [On-base + Slugging Percentage](#odonbaseplussluggingpercentage)

#### <a name="odid">ID</a>

`id` is the ID number used for the player.

#### <a name="odfirst">First</a>

`first` is the player's first name.

#### <a name="odlast">Last</a>

`last` is the player's last name.

#### <a name="odnamedisplay">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="odnumber">Number</a>

`number` is the player's number.

#### <a name="odposition">Position</a>

`pos` is the player's position. It has one of the following values:

+ `C` -- Catcher
+ `1B` -- First Base
+ `2B` -- Second Base
+ `3B` -- Third Base
+ `SS` -- Shortstop
+ `LF` -- Left Field
+ `CF` -- Center Field
+ `RF` -- Right Field
+ `DH` -- Designated Hitter

#### <a name="odatbats">At Bats</a>

`ab` is the total number of at bats for the player in the game.

#### <a name="odhits">Hits</a>

`hit` is the total number of hits for the player in the game.

#### <a name="odbattingaverage">Batting Average</a>

`avg` is the player's batting average, season to date.

#### <a name="odhomeruns">Home Runs</a>

`hr` is the total number of home runs for the player, season to date.

#### <a name="odrbi">RBI</a>

`rbi` is the total number of RBI for the player, season to date.

#### <a name="odsluggingpercentage">Slugging Percentage</a>

`slg` is the player's slugging percentage, season to date.

#### <a name="odonbasepercentage">On-base Percentage</a>

`obp` is the player's on-base percentage, season to date.

#### <a name="odonbaseplussluggingpercentage">On-base + Slugging Percentage</a>

`ops` is the player's on-base plus slugging percentage, season to date.

## <a name="einhole">In Hole Element</a>

The `inhole` element describes the batter in the hole when the game was stopped. It is only present if the `<in_game>` element is also present.

    <inhole id="400290" pos="LF" ab="0" hit="0" avg=".160" hr="0" rbi="2" slg=".200" obp=".250" ops=".450" number="26" last="Kearns" first="Austin" name_display_roster="Kearns"/>

### In Hole Attributes

+ [ID](#inhid)
+ [First](#inhfirst)
+ [Last](#inhlast)
+ [Display Name](#inhnamedisplay)
+ [Number](#inhnumber)
+ [Position](#inhposition)
+ [At Bats](#inhatbats)
+ [Hits](#inhhits)
+ [Batting Average](#inhbattingaverage)
+ [Home Runs](#inhhomeruns)
+ [RBI](#inhrbi)
+ [Slugging Percentage](#inhsluggingpercentage)
+ [On-base Percentage](#inhonbasepercentage)
+ [On-base + Slugging Percentage](#inhonbaseplussluggingpercentage)

#### <a name="inhid">ID</a>

`id` is the ID number used for the player.

#### <a name="inhfirst">First</a>

`first` is the player's first name.

#### <a name="inhlast">Last</a>

`last` is the player's last name.

#### <a name="inhnamedisplay">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="inhnumber">Number</a>

`number` is the player's number.

#### <a name="inhposition">Position</a>

`pos` is the player's position. It has one of the following values:

+ `C` -- Catcher
+ `1B` -- First Base
+ `2B` -- Second Base
+ `3B` -- Third Base
+ `SS` -- Shortstop
+ `LF` -- Left Field
+ `CF` -- Center Field
+ `RF` -- Right Field
+ `DH` -- Designated Hitter

#### <a name="inhatbats">At Bats</a>

`ab` is the total number of at bats for the player in the game.

#### <a name="inhhits">Hits</a>

`hit` is the total number of hits for the player in the game.

#### <a name="inhbattingaverage">Batting Average</a>

`avg` is the player's batting average, season to date.

#### <a name="inhhomeruns">Home Runs</a>

`hr` is the total number of home runs for the player, season to date.

#### <a name="inhrbi">RBI</a>

`rbi` is the total number of RBI for the player, season to date.

#### <a name="inhsluggingpercentage">Slugging Percentage</a>

`slg` is the player's slugging percentage, season to date.

#### <a name="inhonbasepercentage">On-base Percentage</a>

`obp` is the player's on-base percentage, season to date.

#### <a name="inhonbaseplussluggingpercentage">On-base + Slugging Percentage</a>

`ops` is the player's on-base plus slugging percentage, season to date.

## <a name="erunneronfirst">Runner on 1st Base Element</a>

The `<runner_on_1b>` describes the runner on 1st Base when the game was stopped. If a runner was not occupying the base, then the value of all attributes is an empty string. It is only present if the `<in_game>` element is also present.

    <runner_on_1b id="425783" number="17" last="Choo" first="Shin-Soo" name_display_roster="Choo"/>

### Runner on 1st Base Attributes

+ [ID](#r1id)
+ [First](#r1first)
+ [Last](#r1last)
+ [Display Name](#r1namedisplay)
+ [Number](#r1number)

#### <a name="r1id">ID</a>

`id` is the ID number used for the player.

#### <a name="r1first">First</a>

`first` is the player's first name.

#### <a name="r1last">Last</a>

`last` is the player's last name.

#### <a name="r1namedisplay">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="r1number">Number</a>

`number` is the player's number.

## <a name="erunneronsecond">Runner on 2nd Base Element</a>

The `<runner_on_2b>` describes the runner on 2nd Base when the game was stopped. If a runner was not occupying the base, then the value of all attributes is an empty string. It is only present if the `<in_game>` element is also present.

    <runner_on_2b id="488726" number="23" last="Brantley" first="Michael" name_display_roster="Brantley"/>

### Runner on 2nd Base Attributes

+ [ID](#r2id)
+ [First](#r2first)
+ [Last](#r2last)
+ [Display Name](#r2namedisplay)
+ [Number](#r2number)

#### <a name="r2id">ID</a>

`id` is the ID number used for the player.

#### <a name="r2first">First</a>

`first` is the player's first name.

#### <a name="r2last">Last</a>

`last` is the player's last name.

#### <a name="r2namedisplay">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="r2number">Number</a>

`number` is the player's number.

## <a name="erunneronthird">Runner on 3rd Base Element</a>

The `<runner_on_3b>` describes the runner on 3rd Base when the game was stopped. If a runner was not occupying the base, then the value of all attributes is an empty string. It is only present if the `<in_game>` element is also present.

    <runner_on_3b id="" number="" last="" first="" name_display_roster=""/>

### Runner on 3rd Base Attributes

+ [ID](#r3id)
+ [First](#r3first)
+ [Last](#r3last)
+ [Display Name](#r3namedisplay)
+ [Number](#r3number)

#### <a name="r3id">ID</a>

`id` is the ID number used for the player.

#### <a name="r3first">First</a>

`first` is the player's first name.

#### <a name="r3last">Last</a>

`last` is the player's last name.

#### <a name="r3namedisplay">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="r3number">Number</a>

`number` is the player's number.

## <a name="ereview">Review Element</a>

The `<review/>` element describes the challenges for each team.

    <review challenges_away_used="0" challenges_away_remaining="1" challenges_home_used="0" challenges_home_remaining="1"/>

#### Review Attributes

+ [Away Team Challenges Used](#achallengesused)
+ [Away Team Challenges Remaining](#achallengesremaining)
+ [Home Team Challenges Used](#hchallengesused)
+ [Home Team Challenges Remaining](#hchallengesremaining)

#### <a name="achallengesused">Away Team Challenges Used</a>

`challenges_away_used` is the number of challenges used by the away team.

#### <a name="achallengesremaining">Away Team Challenges Remaining</a>

`challenges_away_remaining` is the number of challenges remaining for the away team.

#### <a name="hchallengesused">Home Team Challenges Used</a>

`challenges_home_used` is the number of challenges used by the home team.

#### <a name="hchallengesremaining">Home Team Challenges Remaining</a>

`challenges_home_remaining` is the number of challenges remaining for the home team.
