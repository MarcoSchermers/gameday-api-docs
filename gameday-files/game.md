# game.xml

The game.xml file provides basic game information. It consists of the following elements:

+ [`<game>`](#egame)
+ [`<team/>`](#eteam)
+ [`<stadium/>`](#estadium)

These elements form the following structure:

    <game>
        <team/>
        <team/>
        <stadium/>
    </game>

## <a name="egame">Game Element</a>

The `<game>` element describes basic game information.

    <game type="R" local_game_time="13:05" game_pk="288258" game_time_et="01:05 PM" gameday_sw="P">

### Game Attributes

+ [Game Primary Key](#ggameprimarykey)
+ [Type](#gtype)
+ [Local Game Time](#glocalgametime)
+ [Game Time in EST](#ggametimeest)
+ [Gameday Streaming Web](#ggamedaystreamingweb)

#### <a name="gprimarykey">Game Primary Key</a>

`game_pk` is [presumably] the primary key used in MLB's game database.

#### <a name="gtype">Type</a>

`type` identifies game type. It has one of eight values:

 + `E` -- Exhibition
 + `S` -- Spring Training
 + `R` -- Regular Season
 + `A` -- All Star Game
 + `F` -- Wildcard
 + `D` -- Division Series (ALDS / NLDS)
 + `L` -- League Series (ALCS / NLCS)
 + `W` -- World Series

#### <a name="glocalgametime">Local Game Time</a>

`local_game_time` is the game time local to the home team. The value takes the format `HH:MM` and follows the 24-hour clock convention.

#### <a name="ggametimeest">Game Time in EST</a>

`game_time_et` is the game time in Eastern Time. The value takes the format `HH:MM`, follows the 12-hour clock convention, and is followed by an AM/PM specifier.

#### <a name="ggamedaystreamingweb">Gameday Streaming Web</a>

`gameday_sw` identifies if the game is available for streaming on the web. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes
+ `E` -- Unknown
+ `P` -- Paid

## <a name="eteam">Team Element</a>

The `<team/>` element describes a single team in the game. For a complete listing of MLB team information take a look [here](./team-information.md).

    <team type="home" code="nya" file_code="nyy" abbrev="NYY" id="147" name="NY Yankees" name_full="New York Yankees" name_brief="Yankees" w="52" l="35" division_id="201" league_id="103" league="AL"/>

### Team Attributes

+ [Type](#ttype)
+ [Code](#tcode)
+ [File Code](#tfilecode)
+ [Abbreviation](#tabbreviation)
+ [ID](#tid)
+ [Name](#tname)
+ [Full Name](#tfullname)
+ [Brief Name](#tbriefname)
+ [Wins](#twins)
+ [Losses](#tlosses)
+ [Division ID](#tdivisionid)
+ [League ID](#tleagueid)
+ [League](#tleague)

#### <a name="ttype">Type</a>

`type` identifies the home and away team. It has one of two values:

+ `away`
+ `home`

#### <a name="tcode">Code</a>

`code` is a three-letter identifier. Generally, it is derived from the team's city name however, if the city is home to multiple teams **OR** the city name is longer than one word (e.g. St. Louis), the third letter in the team code is either an `a` denoting the American League or `n` denoting the National League. Using the Cardinals as an example, their `code` value is `sln`.

#### <a name="tfilecode">File Code</a>

`file_code` is [presumably] used to organize the team's Gameday files.

#### <a name="tabbreviation">Abbreviation</a>

`abbrev` is the team's abbreviation.

#### <a name="tid">ID</a>

`id` is the ID number used for the team.

#### <a name="tname">Name</a>

`name` is the team's short name. Generally, this is the team's city however, a handful of cities are home to multiple teams, in which case, the short name includes the nickname. Using New York as an example, the Yankees `name` value is the "NY Yankees" while the Mets' is the "NY Mets".

#### <a name="tfullname">Full Name</a>

`name_full` is the team's full name.

#### <a name="tbriefname">Brief Name</a>

`name_brief` is the team's nickname.

#### <a name="twins">Wins</a>

`w` is the team's win total. This total **includes** the results of the game in question.

#### <a name="tlosses">Losses</a>

`l` is the team's loss total. This total **includes** the results of the game in question.

#### <a name="tdivisionid">Division ID</a>

`division_id` is the ID number for the team's division. It has one of six values:

+ `200` -- American League West
+ `201` -- American League East
+ `202` -- American League Central
+ `203` -- National League West
+ `204` -- National League East
+ `205` -- National League Central

#### <a name="tleagueid">League ID</a>

`league_id` is the ID number used for the team's league. It has one of two values:

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

#### <a name="tleague">League</a>

`league` is the short name for the team's league. It has one of two values:

+ `AL` -- American League
+ `NL` -- National

The following are *uncommon* values:

+ `ACC` -- Atlantic Coast Conference
+ `BE` -- Big East
+ `WBC` -- World Baseball Classic
+ `MEX` -- Mexican League
+ `FSL` -- Unknown
+ `FUT` -- Futures
+ `SOU` -- Southern League
+ `""` -- Empty string with no value

## <a name="estadium">Stadium Element</a>

The `<stadium />` element describes the venue for the game.

    <stadium id="3313" name="Yankee Stadium" venue_w_chan_loc="USNY0172" location="Bronx, NY"/>

### Stadium Attributes

+ [ID](#sid)
+ [Name](#sname)
+ [Venue Weather Channel Code](#svenueweatherchannelcode)
+ [Location](#slocation)

#### <a name="sid">ID</a>

`id` is the ID number used for the venue.

#### <a name="sname">Name</a>

`name` is the venue's name.

#### <a name="svenueweatherchannelcode">Venue Weather Channel Code</a>

`venue_w_chan_loc` is the Weather Channel location code. The value takes the format `USABXXXX` where `AB` is the two letter state abbreviation and `XXXX` is a four digit code, such that the Bronx, NY code is `USNY0172`. This code is used by [AOL Weather](http://weather.aol.com/), [The Weather Channel](http://www.weather.com/), and [Yahoo! Weather](https://weather.yahoo.com/). To view all United States weather location codes take a look [here](https://www.edg3.co.uk/snippets/weather-location-codes/united-states-of-america/).

#### <a name="slocation">Location</a>

`location` is the location of the venue.
