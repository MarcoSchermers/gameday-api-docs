# linescore.xml

The linescore.xml file provides information about scoring during the game. It consists of the following elements:

+ [`<game>`](#egame)
+ [`<linescore>`](#elinescore)
+ [`<winning_pitcher>`](#ewinningpitcher)
+ [`<losing_pitcher>`](#elosingpitcher)
+ [`<save_pitcher>`](#esavepitcher)
+ [`<game_media>`](#egamemedia)
+ [`<media>`](#emedia)

These elements form the following structure:

    <game>
        <linescore/> # multiple elements
        <winning_pitcher/>
        <losing_pitcher/>
        <save_pitcher/>
        <game_media>
            <media/>
        </game_media>
    </game>

## <a name="egame">Game Element</a>

The `<game>` element describes basic game information.

    <game id="2013/10/30/slnmlb-bosmlb-1" venue="Fenway Park" game_pk="379735" time="7:30" time_date="2013/10/30 7:30" time_date_aw_lg="2013/10/30 7:30" time_date_hm_lg="2013/10/30 7:30" time_zone="ET" ampm="PM" first_pitch_et="8:07" away_time="6:30" away_time_zone="CT" away_ampm="PM" home_time="7:30" home_time_zone="ET" home_ampm="PM" game_type="W" tiebreaker_sw="N" original_date="2013/10/30" time_zone_aw_lg="-4" time_zone_hm_lg="-4" time_aw_lg="7:30" aw_lg_ampm="PM" tz_aw_lg_gen="ET" time_hm_lg="7:30" hm_lg_ampm="PM" tz_hm_lg_gen="ET" venue_id="3" scheduled_innings="9" description="World Series Game 6" away_name_abbrev="STL" home_name_abbrev="BOS" away_code="sln" away_file_code="stl" away_team_id="138" away_team_city="St. Louis" away_team_name="Cardinals" away_division="C" away_league_id="104" away_sport_code="mlb" home_code="bos" home_file_code="bos" home_team_id="111" home_team_city="Boston" home_team_name="Red Sox" home_division="E" home_league_id="103" home_sport_code="mlb" day="WED" gameday_sw="P" double_header_sw="N" game_nbr="1" tbd_flag="N" away_games_back="-" home_games_back="-" venue_w_chan_loc="USMA0046" series="World Series" series_num="6" ser_home_nbr="1" ser_games="7" if_necessary="N" gameday_link="2013_10_30_slnmlb_bosmlb_1" away_win="2" away_loss="4" home_win="4" home_loss="2" game_data_directory="/components/game/mlb/year_2013/month_10/day_30/gid_2013_10_30_slnmlb_bosmlb_1" league="NA" top_inning="Y" inning_state="" status="Final" ind="F" inning="9" balls="0" strikes="0" outs="3" away_team_runs="1" home_team_runs="6" away_team_hits="9" home_team_hits="8" away_team_errors="1" home_team_errors="1" wrapup_link="/mlb/gameday/index.jsp?gid=2013_10_30_slnmlb_bosmlb_1&mode=wrap&c_id=mlb" home_preview_link="/mlb/gameday/index.jsp?gid=2013_10_30_slnmlb_bosmlb_1&mode=preview&c_id=mlb" away_preview_link="/mlb/gameday/index.jsp?gid=2013_10_30_slnmlb_bosmlb_1&mode=preview&c_id=mlb" preview="/mlb/gameday/index.jsp?gid=2013_10_30_slnmlb_bosmlb_1&mode=preview&c_id=mlb" tv_station="FOX" home_recap_link="/mlb/gameday/index.jsp?gid=2013_10_30_slnmlb_bosmlb_1&mode=recap&c_id=bos" away_recap_link="/mlb/gameday/index.jsp?gid=2013_10_30_slnmlb_bosmlb_1&mode=recap&c_id=stl" photos_link="/mlb/gameday/index.jsp?gid=2013_10_30_slnmlb_bosmlb_1&mode=photos">

+ [ID](#gid)
+ [Game Primary Key](#gprimarykey)
+ [Original Date](#goriginaldate)
+ [Day](#gday)
+ [Venue ID](#gvenueid)
+ [Venue](#gvenue)
+ [Venue Weather Channel Code](#gvenueweatherchannelcode)
+ [TV Station](#gtvstation)
+ [Type](#gtype)
+ [League](#gleague)
+ [First Pitch ET](#gfirstpitchet)
+ [Time](#gtime)
+ [Time Zone](#gtimezone)
+ [AM / PM](#gampm)
+ [Time Date](#gtimedate)
+ [Away Team Time](#gawaytime)
+ [Away Team Time Zone](#gawaytimezone)
+ [Away Team AM / PM](#gawayampm)
+ [Away Team League Time](#gawayleaguetime)
+ [Away Team League Time Zone](#gawayleaguetimezone)
+ [Away Team League AM / PM](#gawayleagueampm)
+ [Away Team League Time Zone General](#gawayleaguetimezonegeneral)
+ [Away Team League Time Date](#gawayleaguetimedate)
+ [Home Team Time](#ghometime)
+ [Home Team Time Zone](#ghometimezone)
+ [Home Team AM / PM](#ghomeampm)
+ [Home Team League Time](#ghomeleaguetime)
+ [Home Team League Time Zone](#ghomeleaguetimezone)
+ [Home Team League AM / PM](#homeleagueampm)
+ [Home Team League Time Zone General](#ghomeleaguetimezonegeneral)
+ [Home Team League Time Date](#ghomeleaguetimedate)
+ [Scheduled Innings](#gscheduledinnings)
+ [Description](#gdescription)
+ [Game Number](#ggamenumber)
+ [Top of Inning](#gtopinning)
+ [Inning State](#ginningstate)
+ [Status](#gstatus)
+ [Indicator](#gindicator)
+ [Inning](#ginning)
+ [Balls](#gballs)
+ [Strikes](#gstrikes)
+ [Outs](#gouts)
+ [Series](#gseries)
+ [Games in Series](#gseriesgames)
+ [Series Home Number](#gserieshomenumber)
+ [Game Data Directory](#ggamedatadirectory)
+ [Gameday Link](#ggamedaylink)
+ [Photos Link](#gphotoslink)
+ [Wrapup Link](#gwrapuplink)
+ [Away Team Recap Link](#gawayrecaplink)
+ [Home Team Recap Link](#ghomerecaplink)
+ [Preview](#gpreview)
+ [Home Team Preview Link](#ghomepreviewlink)
+ [Away Team Preview Link](#gawaypreviewlink)
+ [Reason](#greason)
+ [Resume Date](#gresumedate)
+ [To Be Determined](#gtbdflag)
+ [If Necessary](#gifnecessary)
+ [Gameday Streaming Web](#ggamedaystreamingweb)
+ [Double Header Streaming Web](#gdoubleheaderstreamingweb)
+ [Tiebreaker Streaming Web](#gtiebreakerstreamingweb)
+ [Away Team ID](#gawayid)
+ [Away Team Code](#gawaycode)
+ [Away Team File Code](#gawayfilecode)
+ [Away Team City](#gawaycity)
+ [Away Team Name](#gawayname)
+ [Away Team Abbreviation](#gawayabbreviation)
+ [Away Team Division](#gawaydivision)
+ [Away Team League ID](#gawayleagueid)
+ [Away Team Sport Code](#gawaysportcode)
+ [Away Team Wins](#gawaywins)
+ [Away Team Losses](#gawaylosses)
+ [Away Team Games Back](#gawaygamesback)
+ [Away Team Games Back Wildcard](#gawaygamesbackwildcard)
+ [Away Team Spring League ID](#gawayspringleagueid)
+ [Away Team Split Squad](#gawaysplitsquad)
+ [Home Team ID](#ghomeid)
+ [Home Team Code](#ghomecode)
+ [Home Team File Code](#ghomefilecode)
+ [Home Team City](#ghomecity)
+ [Home Team Name](#ghomename)
+ [Home Team Abbreviation](#ghomeabbreviation)
+ [Home Team Division](#ghomedivision)
+ [Home Team League ID](#ghomeleagueid)
+ [Home Team Sport Code](#ghomesportcode)
+ [Home Team Wins](#ghomewins)
+ [Home Team Losses](#ghomelosses)
+ [Home Team Games Back](#ghomegamesback)
+ [Home Team Games Back Wildcard](#ghomegamesbackwildcard)
+ [Home Team Spring League ID](#ghomespringleagueid)
+ [Home Team Split Squad](#ghomesplitsquad)
+ [Away Team Runs](#gawayruns)
+ [Away Team Hits](#gawayhits)
+ [Away Team Errors](#gawayerrors)
+ [Home Team Runs](#ghomeruns)
+ [Home Team Hits](#ghomehits)
+ [Home Team Errors](#ghomeerros)

### <a name="gid">ID</a>

`id` is a unique identifer for the game.

### <a name="gprimarykey">Game Primary Key</a>

`game_pk` is [presumably] the primary key used in MLB's game database.

### <a name="goriginaldate">Original Date</a>

`original_date` is the game date in the format `YYYY/MM/DD`

### <a name="gday">Day</a>

`day` is the day of the game. It has one of the following values:

+ `SUN` -- Sunday
+ `MON` -- Monday
+ `TUE` -- Tuesday
+ `WED` -- Wednesday
+ `THU` -- Thursday
+ `FRI` -- Friday
+ `SAT` -- Saturday

### <a name="gvenue">Venue ID</a>

`venue_id` is the ID number used for the venue.

### <a name="gvenueweatherchannelcode">Venue Weather Channel Code</a>

`venue_w_chan_loc` is the Weather Channel location code. The value takes the format `USABXXXX` where `AB` is the two letter state abbreviation and `XXXX` is a four digit code, such that the Bronx, NY code is `USNY0172`. This code is used by [AOL Weather](http://weather.aol.com/), [The Weather Channel](http://www.weather.com/), and [Yahoo! Weather](https://weather.yahoo.com/). To view all United States weather location codes take a look [here](https://www.edg3.co.uk/snippets/weather-location-codes/united-states-of-america/).

### <a name="gtvstation">TV Station</a>

`tv_station` is a comma separted list of TV stations playing the game.

### <a name="gtype">Type</a>

`game_type` identifies game type. It has one of the following values:

 + `E` -- Exhibition
 + `S` -- Spring Training
 + `R` -- Regular Season
 + `A` -- All Star Game
 + `F` -- Wildcard
 + `D` -- Division Series (ALDS / NLDS)
 + `L` -- League Series (ALCS / NLCS)
 + `W` -- World Series

### <a name="gleague">League</a>

`league` is a two-letter identifier that denotes the away and home team leagues respectively. It has one of the following values:

+ `AA` -- American / American
+ `AN` -- American / National
+ `NN` -- National / National
+ `NA` -- National / American

The following are *uncommon* values:

+ `BA` -- College / American
+ `BN` -- College / National
+ `FA` -- Futures / American
+ `FN` -- Futures / National
+ `IA` -- International / American
+ `MN` -- Mexican / National
+ `SN` -- Southern League / National
+ `WA` -- World Baseball Classic / American
+ `WN` -- World Baseball Classic / National

### <a name="gfirstpitchet">First Pitch ET</a>

`first_pitch_et` is the time of the first pitch in Easter Time. The value may be an empty string.

### <a name="gtime">Time</a>

`time` is the start time for the game in Eastern Time. It takes the format `HH:MM` and follows the 12-hour clock convention however, single digit hours are **not** preceded by a `0`.

### <a name="gtimezone">Time Zone</a>

`time_zone` *always* has a value of `ET`.

### <a name="gampm">AM / PM</a>

`ampm` identifies whether the time is AM or PM. It has one of the following values:

+ `AM`
+ `PM`

### <a name="gtimedate">Time Date</a>

`time_date` is the time and date of the game in the format `YYYY/MM/DD HH:MM`. Single digit hours are **not** preceeded by a `0` and it is in Eastern Time.

### <a name="gawaytime">Away Team Time</a>

`away_time` is game time in the away team's local time. It takes the format `HH:MM` and follows the 12-hour clock convention however, single digit hours are **not** preceded by a `0`.

### <a name="gawaytimezone">Away Team Time Zone</a>

`away_time_zone` is the away team's time zone. It has one of the following values:

+ `ET` -- Eastern Time
+ `EST` -- Eastern Standard Time
+ `MT` -- Mountain Time
+ `MST` -- Mountain Standard Time
+ `PT` -- Pacific Time
+ `CT` -- Central Time
+ `CE` -- Central European Time

### <a name="gawayampm">Away Team AM / PM</a>

`away_ampm` identifies the away team's local time as either AM or PM. It has one of the following values:

+ `AM`
+ `PM`

### <a name="gawayleaguetime">Away Team League Time</a>

`time_aw_lg` is the Eastern Standard time for the away team's league. It takes the format `HH:MM` and follows the 12-hour clock convention however, single digit hours are **not** preceded by a `0`.

### <a name="gawayleaguetimezone">Away Team League Time Zone</a>

`time_zone_aw_lg` is the away team's league time zone. It has one of the following values:

+ `0` -- All College Games
+ `-4` -- Both teams are in the same league
+ `-5` -- Teams in opposite leagues OR vs Toronto
+ `-6` -- All Mexican League Games

### <a name="gawayleagueampm">Away Team League AM / PM</a>

`aw_lg_ampm` identifies the away team's league time as either AM or PM. It has one of the following values:

+ `AM`
+ `PM`

### <a name="gawayleaguetimezonegeneral">Away Team League Time Zone General</a>

`tz_aw_lg_gen` is the away team's league general time zone? It has one of the following values:

+ `ET` - Eastern Time
+ `CT` - Central Time

### <a name="gawayleaguetimedate">Away Team League Time Date</a>

`time_date_aw_lg` is away team's league Easter Standard time and date of the game in the format `YYYY/MM/DD HH:MM`. Single digit hours are **not** preceeded by a `0`.

### <a name="ghometime">Home Team Time</a>

`home_time` is game time in the home team's local time. It takes the format `HH:MM` and follows the 12-hour clock convention however, single digit hours are **not** preceded by a `0`.

### <a name="ghometimezone">Home Team Time Zone</a>

`home_time_zone` is the home team's time zone. It has one of the following values:

+ `ET` -- Eastern Time
+ `MT` -- Mountain Time
+ `MST` -- Mountain Standard Time
+ `PT` -- Pacific Time
+ `CT` -- Central Time

### <a name="ghomeampm">Home Team AM / PM</a>

`home_ampm` identifies the home team's local time as either AM or PM. It has one of the following values:

+ `AM`
+ `PM`

### <a name="ghomeleaguetime">Home Team League Time</a>

`time_hm_lg` is the Eastern Standard time for the away team's league. It takes the format `HH:MM` and follows the 12-hour clock convention however, single digit hours are **not** preceded by a `0`.

### <a name="ghomeleaguetimezone">Home Team League Time Zone</a>

`time_zone_hm_lg` is the home team's league time zone. It has one of the following values:

+ `-4` -- Both teams are in the same league
+ `-5` -- Teams in opposite leagues OR vs Toronto

### <a name="homeleagueampm">Home Team League AM / PM</a>

`hm_lg_ampm` identifies the away team's league time as either AM or PM. It has one of the following values:

+ `AM`
+ `PM`

### <a name="ghomeleaguetimezonegeneral">Home Team League Time Zone General</a>

`tz_hm_lg_gen` is the away team's league general time zone? It has one of the following values:

+ `ET`

### <a name="ghomeleaguetimedate">Home Team League Time Date</a>

`time_date_hm_lg` is away team's league Easter Standard time and date of the game in the format `YYYY/MM/DD HH:MM`. Single digit hours are **not** preceeded by a `0`.

### <a name="gscheduledinnings">Scheduled Innings</a>

`scheduled_innings` is the number of scheduled innings for the game. It has one of the following values:

+ `7`
+ `9`

### <a name="gdescription">Description</a>

`description` is a text description of the game. This attribute may not be present.

### <a name="ggamenumber">Game Number</a>

`game_nbr` is the game number. If present, it has one of the following values:

+ `1` (A value of 1 does **not** denote a doubleheader)
+ `2`

### <a name="gtopinning">Top of Inning</a>

`top_inning` identifies if the game concluded in the top of the last scheduled inning. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes

### <a name="ginningstate">Inning State</a>

`inning_state` is a text description of the inning when the game concluded. It appears that this value is an empty string.

### <a name="gstatus">Status</a>

`status` identifies the game status. It has one of the following values:

+ `Final`
+ `Completed Early`
+ `Postponed`
+ `Cancelled`
+ `Preview`
+ `Game Over`

### <a name="gindicator">Indicator</a>

`ind` identifies the game status as an abbreviation. It has one of the following values:

+ `F` -- Final
+ `FT` -- Final and score tied
+ `FR` -- Final and called due to rain
+ `DR` -- Delayed due to rain
+ `DS` -- Delayed due to snow
+ `CR` -- Called due to rain
+ `S` -- Unknown
+ `DO` -- (Delayed Other?)
+ `FO` -- Final (completed early, reason: Other)
+ `O` -- (Other?)

### <a name="ginning">Inning</a>

`inning` is the number of innings played.

### <a name="gballs">Balls</a>

`balls` is the number of balls at the end of the game. May not be present. Does **not** appear to have a value other than `0`.

### <a name="gstrikes">Strikes</a>

`strikes` is the number of strikes at the end of the game. May not be present. Does **not** appear to have a value other than `0`.

### <a name="gouts">Outs</a>

`outs` is the number of outs in the last inning. It has one of the following values:

+ `0`
+ `1`
+ `2`
+ `3`

### <a name="gseries">Series</a>

`series` identifies the current series. If present, it has one of the following values:

+ `AL Wild Card`
+ `NL Wild Card`
+ `ALDS`
+ `NLDS`
+ `ALCS`
+ `NLCS`
+ `World Series`

### <a name="gseriesgames">Games in Series</a>

`series_num` is the game number in the series. If present, it has one of the following values:

+ `1`
+ `2`
+ `3`
+ `4`
+ `5`
+ `6`
+ `7`

### <a name="gserieshomenumber">Series Home Number</a>

`ser_home_nbr` identifies the home game number for the game in the series. If present, it has one of the following values:

+ `1`
+ `2`
+ `3`
+ `4`

### <a name="ggamedatadirectory">Game Data Directory</a>

`game_data_directory` is the path to the top-level directory for the game. It is relative to `http://gd2.mlb.com/`.

### <a name="ggamedaylink">Gameday Link</a>

`gameday_link` is the gameday ID component of the game URL.

### <a name="gphotoslink">Photos Link</a>

`photos_link` is the path to the photo slideshow. It is relative to `mlb.mlb.com`

### <a name="gwrapuplink">Wrapup Link</a>

`wrapup_link` is the path to the game summary. It is relative to `mlb.mlb.com`.

### <a name="gawayrecaplink">Away Team Recap Link</a>

`away_recap_link` is the path to the away team's recap. It is relative to `mlb.mlb.com`.

### <a name="ghomerecaplink">Home Team Recap Link</a>

`home_recap_link` is the path to the home team's recap. It is relative to `mlb.mlb.com`.

### <a name="gpreview">Preview</a>

`preview` is the path to the game preview. It is relative to `mlb.mlb.com`.

### <a name="gawaypreviewlink">Away Team Preview Link</a>

`away_preview_link` is the path to the away team's game preview. It is relative to `mlb.mlb.com`.

### <a name="ghomepreviewlink">Home Team Preview Link</a>

`home_preview_link` is the path to the home team's game preview. It is relative to `mlb.mlb.com`.

### <a name="greason">Reason</a>

`reason` is the reason for game stoppage. If present, it has one of the following values:

+ `Tied`
+ `Rain`
+ `Snow`
+ `Other`

### <a name="gresumedate">Resume Date</a>

`resume_date` is the resume date for a stopped game. It may not be present.

### <a name="gtbdflag">To Be Determined</a>

`tbd_flag` identifies if the resume date is to be determined. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes

### <a name="gifnecessary">If Necessary</a>

`if_necessary` identifies if the game is necessary. If present, it has one of the following values:

+ `N` -- No

### <a name="ggamedaystreamingweb">Gameday Streaming Web</a>

`gameday_sw` identifies if the game is available for streaming on the web. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes
+ `E` -- Unknown
+ `P` -- Paid

### <a name="gdoubleheaderstreamingweb">Double Header Streaming Web</a>

`double_header_sw` identifies if the double header is available for streaming on the web. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes
+ `S` -- Subscription

### <a name="gtiebreakerstreamingweb">Tiebreaker Streaming Web</a>

`tiebreaker_sw` identifies if the tiebreaker is available for streaming on the web. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes

### <a name="gawayid">Away Team ID</a>

`away_team_id` is the ID number used for the away team.

### <a name="gawaycode">Away Team Code</a>

`away_code` is a three-letter identifier. Generally, it is derived from the team's city name however, if the city is home to multiple teams **OR** the city name is longer than one word (e.g. St. Louis), the third letter in the team code is either an `a` denoting the American League or `n` denoting the National League. Using the Cardinals as an example, their `away_code` value is `sln`.

### <a name="gawayfilecode">Away Team File Code</a>

`away_file_code` is [presumably] used to organize the away team's Gameday files.

### <a name="gawaycity">Away Team City</a>

`away_team_city` is the team's city name.

### <a name="gawayname">Away Team Name</a>

`away_team_name` is the away team's nickname.

### <a name="gawayabbreviation">Away Team Abbreviation</a>

`away_name_abbrev` is the away team's abbreviation.

### <a name="gawaydivision">Away Team Division</a>

`away_division` identifies the away team's division. It has one of the following values:

+ `E` -- East
+ `W` -- West
+ `C` -- Central

The following are *uncommon* values:

+ `N` -- Mexican League
+ `S` -- Unknown
+ `D` -- International (Canada, Italy, Mexico, USA)
+ `A` -- International (Japan)
+ `B` -- International (Netherlands)

### <a name="gawayleagueid">Away Team League ID</a>

`away_league_id` is the ID number used for the away team's league. It has one of following values:

+ `103` -- American League
+ `104` -- National League

The following are *uncommon* values:

+ `107` -- College Baseball
+ `108` -- College
+ `111` -- Farm System?
+ `123` -- Unknown
+ `125` -- Mexican
+ `160` -- International
+ `580` -- International
+ `590` -- Futures (Minor Leagues)

### <a name="gawaysportcode">Away Team Sport Code</a>

`away_sport_code` identifies the sport code for the away team. It has one of the following values:

+ `mlb` -- Major League Baseball

The following are *uncommon* values:

+ `afa` -- Unknown
+ `aax` -- Farm System?
+ `bbc` -- College Baseball
+ `int` -- International
+ `aaa` -- Mexican League
+ `min` -- Minor League Baseball

### <a name="gawaywins">Away Team Wins</a>

`away_win` is the total number of away team wins **including** the game in question.

### <a name="gawaylosses">Away Team Losses</a>

`away_loss` is the total number of away team losses **including** the game in question.

### <a name="gawaygamesback">Away Team Games Back</a>

`away_games_back` is the total number of games back for the away team. If the away team is leading the division, the value is `-`.

### <a name="gawaygamesbackwildcard">Away Team Games Back Wildcard</a>

`away_games_back_wildcard` is the total number of games back in the wild card for the away team. This may not be present. If the away team is leading the wild card, the value is `-`.

### <a name="gawayspringleagueid">Away Team Spring League ID</a>

`away_league_id_spring` is the ID number used for the away team's Spring Training League. If present, it has one of the following values:

+ `114` -- Cactus League
+ `115` -- Grapefruit League

### <a name="gawaysplitsquad">Away Team Split Squad</a>

`away_split_squad` identifies if the away team is a split squad. If present, it has one of the following values:

+ `N` -- No
+ `Y` -- Yes

### <a name="ghomeid">Home Team ID</a>

`home_team_id` is the ID number used for the home team.

### <a name="ghomecode">Home Team Code</a>

`home_code` is a three-letter identifier. Generally, it is derived from the team's city name however, if the city is home to multiple teams **OR** the city name is longer than one word (e.g. St. Louis), the third letter in the team code is either an `a` denoting the American League or `n` denoting the National League. Using the Cardinals as an example, their `home_code` value is `sln`.

### <a name="ghomefilecode">Home Team File Code</a>

`home_file_code` is [presumably] used to organize the home team's Gameday files.

### <a name="ghomecity">Home Team City</a>

`home_team_city` is the home team's city name.

### <a name="ghomename">Home Team Name</a>

`home_team_name` is the home team's nickname.

### <a name="ghomeabbreviation">Home Team Abbreviation</a>

`home_name_abbrev` is the home team's abbreviation.

### <a name="ghomedivision">Home Team Division</a>

`home_division` identifies the away team's division. It has one of the following values:

+ `E` -- East
+ `W` -- West
+ `C` -- Central

### <a name="ghomeleagueid">Home Team League ID</a>

`home_league_id` is the ID number used for the away team's league. It has one of following values:

+ `103` -- American League
+ `104` -- National League

### <a name="ghomesportcode">Home Team Sport Code</a>

`home_sport_code` identifies the sport code for the away team. It has the following value:

+ `mlb` -- Major League Baseball

### <a name="ghomewins">Home Team Wins</a>

`home_win` is the total number of home team wins **including** the game in question.

### <a name="ghomelosses">Home Team Losses</a>

`home_loss` is the total number of home team losses **including** the game in question.

### <a name="ghomegamesback">Home Team Games Back</a>

`home_games_back` is the total number of games back for the away team. If the home team is leading the division, the value is `-`.

### <a name="ghomegamesbackwildcard">Home Team Games Back Wildcard</a>

`home_games_back_wildcard` is the total number of games back in the wild card for the home team. This may not be present. If the home team is leading the wild card, the value is `-`.

### <a name="ghomespringleagueid">Home Team Spring League ID</a>

`home_league_id_spring` is the ID number used for the home team's Spring Training League. If present, it has one of the following values:

+ `114` -- Cactus League
+ `115` -- Grapefruit League

### <a name="ghomesplitsquad">Home Team Split Squad</a>

`home_split_squad` identifies if the home team is a split squad. If present, it has one of the following values:

+ `N` -- No
+ `Y` -- Yes

### <a name="gawayruns">Away Team Runs</a>

`away_team_runs` is the total number of runs by the away team.

### <a name="gawayhits">Away Team Hits</a>

`away_team_hits` is the total number of hits by the away team.

### <a name="gawayerrors">Away Team Errors</a>

`away_team_errors` is the total number of errors by the away team.

### <a name="ghomeruns">Home Team Runs</a>

`home_team_runs` is the total number of runs by the home team.

### <a name="ghomehits">Home Team Hits</a>

`home_team_hits` is the total number of hits by the home team.

### <a name="ghomeerrors">Home Team Errors</a>

`home_team_errors` is the total number of errors by the home team.

## <a name="elinescore">Linescore Element</a>

The `<linescore/>` element describes a single inning of scoring.

    <linescore inning="1" home_inning_runs="1" away_inning_runs="0"/>

### Linescore Attributes

+ [Away Team Runs](#lawayruns)
+ [Home Team Runs](#lhomeruns)
+ [Inning](#linning)

#### <a name="lawayruns">Away Team Runs</a>

`away_inning_runs` is the total runs scored by the away team.

#### <a name="lhomeruns">Home Team Runs</a>

`home_inning_runs` is the total runs scored by the home team.

#### <a name="linning">Inning</a>

`inning` is the inning number.


## <a name="ewinningpitcher">Winning Pitcher Element</a>

The `<winning_pitcher/>` element describes the winning pitcher.

    <winning_pitcher first_name="John" first="John" id="407793" last_name="Lackey" last="Lackey" name_display_roster="Lackey" wins="1" losses="1" era="2.57" s_wins="" s_losses="" s_era=""/>

### Winning Pitcher Attributes

+ [ID](#wpid)
+ [First Name](#wpfirstname)
+ [Last Name](#lplastname)
+ [First](#wpfirst)
+ [Last](#wplast)
+ [Display Name](#wpdisplayname)
+ [Wins](#wpwins)
+ [Losses](#wplosses)
+ [ERA](#wpera)
+ [Season Wins](#wpseasonwins)
+ [Season Losses](#wpseasonlosses)
+ [Season ERA](#wpseasonera)

#### <a name="wpid">ID</a>

`id` is the ID number used for the player.

#### <a name="wpfirstname">First Name</a>

`first_name` is the player's first name.

#### <a name="lplastname">Last Name</a>

`last_name` is the player's last name.

#### <a name="wpfirst">First</a>

`first` is the player's first name.

#### <a name="wplast">Last</a>

`last` is the player's last name.

#### <a name="wpdisplayname">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="wpwins">Wins</a>

`wins` is the player's win total, season to date.

#### <a name="wplosses">Losses</a>

`losses` is the player's loss total, season to date.

#### <a name="wpera">ERA</a>

`era` is the player's ERA, season to date.

#### <a name="wpseasonwins">Season Wins</a>

`s_wins` is the player's season win total. The value appears to be an empty string.

#### <a name-"wpseasonlosses">Season Losses</a>

`s_losses` is the player's season loss total. The value appears to be an empty string.

#### <a name-"wpseasonera">Season ERA</a>

`s_era` is the player's season ERA. The value appears to be an empty string.

## <a name="elosingpitcher">Losing Pitcher Element</a>

The `<losing_pitcher/>` element describes the losing pitcher.

    <losing_pitcher first_name="Michael" first="Michael" id="608379" last_name="Wacha" last="Wacha" name_display_roster="Wacha" wins="1" losses="1" era="7.45" s_wins="" s_losses="" s_era=""/>

### Losing Pitcher Attributes

+ [ID](#lpid)
+ [First Name](#lpfirstname)
+ [Last Name](#lplastname)
+ [First](#lpfirst)
+ [Last](#lplast)
+ [Display Name](#lpdisplayname)
+ [Wins](#lpwins)
+ [Losses](#lplosses)
+ [ERA](#lpera)
+ [Season Wins](#lpseasonwins)
+ [Season Losses](#lpseasonlosses)
+ [Season ERA](#lpseasonera)

#### <a name="lpid">ID</a>

`id` is the ID number used for the player.

#### <a name="lpfirstname">First Name</a>

`first_name` is the player's first name.

#### <a name="lplastname">Last Name</a>

`last_name` is the player's last name.

#### <a name="lpfirst">First</a>

`first` is the player's first name.

#### <a name="lplast">Last</a>

`last` is the player's last name.

#### <a name="lpdisplayname">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="lpwins">Wins</a>

`wins` is the player's win total, season to date.

#### <a name="lplosses">Losses</a>

`losses` is the player's loss total, season to date.

#### <a name="lpera">ERA</a>

`era` is the player's ERA, season to date.

#### <a name="lpseasonwins">Season Wins</a>

`s_wins` is the player's season win total. The value appears to be an empty string.

#### <a name="lpseasonlosses">Season Losses</a>

`s_losses` is the player's season loss total. The value appears to be an empty string.

#### <a name="lpseasonera">Season ERA</a>

`s_era` is the player's season ERA. The value appears to be an empty string.

## <a name="esavepitcher">Saving Pitcher Element</a>

The `<save_pitcher/>` element describes the saving pitcher. If a save was not recorded, all attributes will have an empty string value *except* for `wins`, `losses`, and `saves` which will have a value of `0`.

    <save_pitcher first_name="Mariano" first="Mariano" id="121250" last_name="Rivera" last="Rivera" name_display_roster="Rivera, Ma" wins="1" losses="1" era="1.85" s_wins="" s_losses="" s_era="" saves="22"/>

### Saving Pitcher Attributes

+ [ID](#spid)
+ [First Name](#spfirstname)
+ [Last Name](#splastname)
+ [First](#spfirst)
+ [Last](#splast)
+ [Display Name](#spdisplayname)
+ [Wins](#spwins)
+ [Losses](#splosses)
+ [ERA](#spera)
+ [Season Wins](#spseasonwins)
+ [Season Losses](#spseasonlosses)
+ [Season ERA](#spseasonera)

#### <a name="spid">ID</a>

`id` is the ID number used for the player.

#### <a name="spfirstname">First Name</a>

`first_name` is the player's first name.

#### <a name="splastname">Last Name</a>

`last_name` is the player's last name.

#### <a name="spfirst">First</a>

`first` is the player's first name.

#### <a name="splast">Last</a>

`last` is the player's last name.

#### <a name="spdisplayname">Display Name</a>

`name_display_roster` is the player's name as it appears on the roster.

#### <a name="spwins">Wins</a>

`wins` is the player's win total, season to date.

#### <a name="splosses">Losses</a>

`losses` is the player's loss total, season to date.

#### <a name="spsaves">Saves</a>

`saves` is the player's save total, season to date.

#### <a name="spera">ERA</a>

`era` is the player's ERA, season to date.

#### <a name="spseasonwins">Season Wins</a>

`s_wins` is the player's season win total. The value appears to be an empty string.

#### <a name="spseasonlosses">Season Losses</a>

`s_losses` is the player's season loss total. The value appears to be an empty string.

#### <a name="spseasonera">Season ERA</a>

`s_era` is the player's season ERA. The value appears to be an empty string.

## <a name="egamemedia">Game Media Element</a>

The `<game_media>` element is a container element that does not have any attributes.

## <a name="emedia">Media Element</a>

The `<media/>` element describes basic media information.

    <media type="game" calendar_event_id="14-379735-2013-10-30" start="2013-10-30T19:30:00-0400" title="STL @ BOS" has_mlbtv="true" free="NO" media_state="media_archive" thumbnail="http://mediadownloads.mlb.com/mlbam/preview/slnbos_379735_th_7_preview.jpg"/>

### Media Attributes

+ [Type](#mtype)
+ [Title](#mtitle)
+ [Calendar Event ID](#mcaleventid)
+ [Thumbnail](#mthumbnail)
+ [Start](#mstart)
+ [Has MLBTV](#mhasmlbtv)
+ [Free](#mfree)
+ [Media State](#mmediastate)

#### <a name="mtype">Type</a>

`type` identifies the type of event. It has one of the following values:

+ `game`

#### <a name="mtitle">Title</a>

`title` is the title of the game.

#### <a name="mcaleventid">Calendar Event ID</a>

`calendar_event_id` is the event ID in the format `14-game_pk-YYYY-MM-DD`

#### <a name="mthumbnail">Thumbnail</a>

`thumbnail` is a preview image for the game.

#### <a name="mstart">Start</a>

`start` is the start time for the event. It takes the format `YYYY-MM-DD-THH:MM:SS-XXXX` where `XXXX` represents the UTC offset.

#### <a name="mhasmlbtv">Has MLBTV</a>

`has_mlbtv` identifies MLB TV availability. It has one of the following values:

+ `true`

#### <a name="mfree">Free</a>

`free` identifies if the game is free to view. It has one of the following values:

+ `NO`
+ `IPHONE,ANDROID,IPAD,IPHONE_MEDIAPLAYER`
+ `ALL`

#### <a name="mmediastate">Media State</a>

`media_state` identifies the state of the media. It has one of the following values:

+ `media_on`
+ `media_off`
+ `media_done`
+ `media_staging`
+ `media_archive`
