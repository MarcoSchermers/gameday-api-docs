# MLB Gameday API Primer 

## Introduction

The MLB Gameday API is a collection of XML files hosted on an [MLB server](http://gd2.mlb.com/). As you would expect, a file is retrieved through a request that is made to a specific URL. Rather than attempt to explain the URL structure without a reference point, a sample URL is provided below and then described in detail.

	http://gd2.mlb.com/components/game/mlb/year_2011/month_07/day_09/gid_2011_07_09_tbamlb_nyamlb_1/boxscore.xml
	
A request made with this URL asks for the `boxscore.xml` Gameday file from the Tampa Bay Rays vs. New York Yankees game on July 9, 2011. To the astute fan, this is the game when Derek Jeter recorded his 3000<sup>th</sup> hit. The `boxscore.xml` file is one of the Gameday API files and as you might imagine, it describes the box score for the game in detail. If a Gameday URL has been constructed properly, the last path component will **always** be a Gameday API file. As you may have inferred from the URL above, the Gameday API files are organized in a hierarchy of directories on the MLB server. Now that you've seen a URL and understand how the files are organized, let's take a closer look at the URL structure.

## Gameday URL Components

The Gameday API URL structure may seem overwhelming at first glance. However, with the knowledge of how API files are organized on the server and an understanding of the individual URL components, a Gameday URL will quickly become intuitive and self-documenting. The following is an overview of the URL components. 

### Protocol

The HTTP protocol is used to retrieve a Gameday API file.

### Hostname

The hostname is `gd2.mlb.com` and is the base URL of the API.

### Components  Directory

The `/components` relative path is a directory that contains information that is all but irrelevant to the Gameday API files you are interested in. It has the `game` sub-directory which is described below.

**Notes** 

* If you haven't had the opportunity to read the MLB Advanced Media, L.P. copyright for the Gameday data please do so. You can find it in the `components` directory [here](http://gd2.mlb.com/components/copyright.txt).

### Game Directory

The `/components/game` relative path is a directory that much like it's parent, contains information that is all but irrelevant to the Gameday API files you are interested in. It does have the `mlb` sub-directory, which is the starting point for locating Gameday API files.

### MLB Directory

The `/components/game/mlb` relative path is a directory that contains several files and year sub-directories ranging from 1909 to present (and a few from the future). 

**Notes** 

* Information from years outside of 2008 - Present may have incomplete game data and fail to have Pitchf/x data which was established in 2007. 
* If your goal is to find the most complete game data set, it is recommended that you focus on 2008 - Present.

### Year Directory

The `/components/game/mlb/year_YYYY` relative path is the root directory for all games in a particular year. Each year directory contains a `batters`, `pitchers`, `media`, `mobile` sub-directory as well as one for each month of the year.

**Notes**

* `YYYY` represents the four digit year.
* Only the months during the season contain data (includes spring training)

### Month Directory

The `/components/game/mlb/year_YYYY/month_MM` relative path is a directory that contains a sub-directory for each day in the month.

**Notes**

* 'MM' represents the two digit month (single digit month is prefixed with a zero).

### Day Directory

The `/components/game/mlb/year_YYYY/month_MM/day_DD` relative path is a directory that contains a sub-directory for each game played on that day as well as various files and directories describing the games played. These additional files and directories will be documented as they are part of the overall MLB Gameday API, however the game sub-directories contain the necessary set of files to analyze a single game.

**Notes**: 

* 'DD' represents the two digit day (single digit day is prefixed with a zero).

### Game Data Directory

The `/components/game/mlb/year_YYYY/month_MM/day_DD/gid_*` relative path is a directory known as the game data directory. This is where the Gameday API files are stored for a particular game.  It contains several top-level files which describe game data as well as sub-directories that organize batter, pitcher, inning, media, notification, and premium information data files. The Gameday API files will be listed below with a link to a complete file reference.

Now that you know *where* the Gameday files are stored for a game, you need to know *how* the game data directory path component is structured. Rather than scroll back to the top, the sample game data directory component from our example is provided below.

	/gid_2011_07_09_tbamlb_nyamlb_1
	
* You can refer to this relative path as the game ID path or GID path.
* It **always** takes the form `/gid_YYYY_MM_DD_atcasc_htchsc_d`

	* `YYYY` --  four digit year (same as year component)
	* `MM` -- two digit month (same as month component)
	* `DD` -- two digit day (same as day component)
	* `atc` -- three-letter away team code
	* `asc` -- three-letter away team sport code
	* `htc` -- three-letter home team code
	* `hsc` -- three-letter home team sport code
	* `d` -- one digit game number (either 1 or 2)
	
This may seem like a lot to remember but keep in mind that the year, month, and day placeholders are exactly the same as the year, month, and day path values from earlier in the URL. The game number simply identifies the game number between the two teams on the particular date. A value of `2` identifies it as the second game of a doubleheader while all other games have a value of `1`. Therefore, a value of `1` does **NOT** imply the first game of a doubleheader. This leaves the section identifying the team's participating in the game. Let's start with the home and away team codes.

As mentioned, the home and away team codes are a three-letter *unique* identifier. Each team in Major League Baseball has been provided a team code and a listing of all team information as it pertains to the MLB Gameday API can be found [here](./team-information.md). The team code is generally derived from the city name of each team (e.g. the Boston Red Sox team code is `bos` and the Cincinnati Reds team code is `cin`). In some cases, the city name consists of multiple words **OR** the city is home to multiple teams and doesn't allow for a similar derivation. In both cases, the team code remains a three-letter identifier. However, the last letter is either an `a` or an `n` which identifies the American or National League. A few examples will help clarify.

City Name With Multiple Words

* `kca` -- Kansas City Royals
* `sln` -- St. Louis Cardinals

City with Multiple Teams

* `nya` -- New York Yankees
* `nyn` -- New York Mets
* `cha` -- Chicago White Sox
* `chn` -- Chicago Cubs

With this knowledge, you now understand how we are able to determine that the Tampa Bay Rays were the visitors and the New York Yankees the home team from the `tba` and `nya` in our sample URL. This does **NOT** imply that the game takes place at the home team's stadium (Spring Training games are also recorded). However, information about the game location can be found in specific Gameday API files.

The last piece of information to understand is the three-letter home and away team sport code. For all Major League Baseball games, both the away team and home team sport code will have a value of `mlb`. However, analysis of games between 2011 and 2013, has shown six additional team sport codes (all applied to the away team). They are as follows:

+ `afa` -- Unknown
+ `aax` -- Farm System?
+ `bbc` -- College Baseball
+ `int` -- International
+ `aaa` -- Mexican League
+ `min` -- Minor League Baseball

In an effort to provide as complete a reference to the MLB Gameday API as possible, there are instances where additional values are provided for academic if not for popular use cases. More likely than not, you are interested in Major League Baseball games and will not have to worry about values other than `mlb`. This concludes the overview of Gameday URL components. Next up is an overview of the game data directory contents.

## Game Data Directory Contents

As mentioned, the game data directory is where the Gameday API files are stored for a particular game. This section is meant to list the game data directory contents. The following is a description of the files that *may* be included in a game data directory. More often than not, the majority of files will be present. However there are instances where certain files are not included (e.g. `emailSource.xml` is not included for Spring Training games).

### Top-level Files

* `atv_feed_selection.xml`
* `atv_game_events.xml`
* `atv_preview.xml`
* `atv_preview_noscores.xml`
* `atv_runScoringPlays.xml`
* `badges.xml`
* `bench.xml`
* `benchO.xml`
* `bis_boxscore.xml`
* `boxscore.xml`
* `emailSource.xml`
* `eventLog.xml`
* `game.xml`
* `game_events.xml`
* `gamecenter.xml`
* `gameday_Syn.xml`
* `linescore.xml`
* `miniscoreboard.xml`
* `players.xml`
* `plays.xml`
* `rawboxscore.xml`

### Sub-directories

* `batters/`
* `inning/`
* `media/`
* `notifications/`
* `onbase/`
* `pitchers/`
* `premium/`

### Non-XML Files

The majority of the Gameday API files are in the XML format while there are a few JSON and PLIST files. Due to the fact that the JSON files have XML counterparts and that the majority of files are XML, the JSON files have not been properly documented. The same goes for the PLIST files which have XML counterparts in the atv_* files. PLIST files are used by the MLB.TV application on the Apple TV. Below are a list of the JSON and PLIST files you may come across.

* `boxscore.json`
* `game_events.json`
* `linescore.json`
* `plays.json`
* `feed_selection.plist`
* `game_events.plist`
* `preview.plist`
* `runScoringPlays.plist`

## Gameday API File Path

Using the knowledge from the game data directory contents, you are now able to construct a relative path *from* the game data directory *to* the desired Gameday API file. In our example URL, the last path component was `/boxscore.xml` which is a top-level file in the game data directory. This just as easily could have been the relative path `/inning/inning_all.xml` which would have made a request to the `inning_all.xml` Gameday API file. It is important to remember that the last path component will **always** be the name of a Gameday API file. Of course, the location of a particular file is dependent on where it is stored and the relevant path *from* the game data directory.

## Conclusion

This concludes our overview of the MLB Gameday API. Although far from an exhaustive description, this primer should have provided you with enough information to get started looking at games of interest and get you moving in the right direction. There is an enormous amount of data provided by MLB, and understanding it's content and structure is no small feat. However, by using the Gameday API file references found on this site you will lessen the learning curve and have more time doing what interests you, analyzing a great set of data. Feel free to send me an [email](mailto:brianmpalma@gmail.com) or [tweet](https://twitter.com/brianmpalma) with any questions, concerns or comments regarding this primer or any of the pages on the site. If you're familiar with GitHub and would like to contribute, fork the [repository](https://github.com/brianmpalma/gameday-api-docs) and send along a pull request. Thank you for taking the time to check out the site, dig in, and have fun!
