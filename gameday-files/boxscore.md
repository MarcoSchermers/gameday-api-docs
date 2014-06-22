# boxscore.xml

The boxscore.xml file provides box score information. It consists of the following elements:

+ [`<boxscore>`](#eboxscore)
+ [`<linescore>`](#elinescore)
+ [`<inning_line_score>`](#einninglinescore)
+ [`<pitching>`](#epitching)
+ [`<pitcher>`](#epitcher)
+ [`<batting>`](#ebatting)
+ [`<batter>`](#ebatter)
+ [`<note>`](#enote)
+ [`<text_data>`](#etextdata)
+ [`<game_info>`](#egameinfo)

These elements form the following structure:

    <boxscore>
        <linescore>
            <inning_line_score/> # multiple elements
        </linescore>
        <pitching>
            <pitcher></pitcher> # multiple elements, most are empty: <pitcher/>
        </pitching>
        <batting>
            <batter/> # multiple elements
            <text_data></text_data>
            <note></note>
        </batting>
        <pitching>
            <pitcher></pitcher> # multiple elements, most are empty: <pitcher/>
        </pitching>
        <batting>
            <batter> # multiple elements
            <note></note>
        </batting>
        <game_info></game_info>
    </boxscore>

## <a name="eboxscore">Boxscore Element</a>

The `<boxscore>` element describes basic game and team information.

    <boxscore game_id="2011/07/09/tbamlb-nyamlb-1" game_pk="288258" venue_id="3313" venue_name="Yankee Stadium" home_sport_code="mlb" away_team_code="tba" home_team_code="nya" away_id="139" home_id="147" away_fname="Tampa Bay Rays" home_fname="New York Yankees" away_sname="Tampa Bay" home_sname="NY Yankees" date="July 9, 2011" away_wins="49" away_loss="40" home_wins="52" home_loss="35" status_ind="F">

### Boxscore Attributes

+ [Game ID](#bgid)
+ [Game Primary Key](#bgameprimarykey)
+ [Date](#bdate)
+ [Status Indicator](#bstatusind)
+ [Venue Name](#bvenuename)
+ [Venue ID](#bvenueid)
+ [Away Team ID](#bawayid)
+ [Away Team Code](#bawaycode)
+ [Away Team Full Name](#bawayfullname)
+ [Away Team Short Name](#bawayshortname)
+ [Away Team Wins](#bawaywins)
+ [Away Team Losses](#bawaylosses)
+ [Home Team Sport Code](#bhomesportcode)
+ [Home Team ID](#bhomeid)
+ [Home Team Code](#bhomecode)
+ [Home Team Full Name](#bhomefullname)
+ [Home Team Short Name](#bhomeshortname)
+ [Home Team Wins](#bhomewins)
+ [Home Team Losses](#bhomelosses)

### <a name="bgid">Game ID</a>

`game_id` is a unique identifer for the game.

### <a name="bgameprimarykey">Game Primary Key</a>

`game_pk` is [presumably] the primary key used in MLB's game database.

### <a name="bdate">Date</a>

`date` is the date for the game.

### <a name="bstatusind">Status Indicator</a>

`status_ind` is the status for the game. It is one of the following values:

+ `F` -- Final
+ `FT` -- Final and score tied
+ `FR` -- Final and called due to rain
+ `I` -- Interrupted due to rain
+ `PR` -- Postponed due to rain
+ `IR` -- Interrupted due to rain
+ `DR` -- Delayed due to rain
+ `P` -- Postponed due to rain
+ `DO` -- (Delayed Other?)
+ `FO` -- Final (completed early, reason: Other)
+ `O` -- (Other?)

### <a name="bvenuename">Venue Name</a>

`venue_name` is the venue's name.

### <a name="bvenueid">Venue ID</a>

`venue_id` is the ID number used for the venue.

### <a name="bawayid">Away Team ID</a>

`away_id` is the ID number used for the away team.

### <a name="bawaycode">Away Team Code</a>

`away_team_code` is the team code for the away team.

### <a name="bawayfullname">Away Team Full Name</a>

`away_fname` is the away team's full name.

### <a name="bawayshortname">Away Team Short Name</a>

`away_sname` is the away team's short name.

### <a name="bawaywins">Away Team Wins</a>

`away_wins` is the away team's total wins **including** the game in question.

### <a name="bawaylosses">Away Team Losses</a>

`away_loss` is the away team's total losses **including** the game in question.

### <a name="bhomesportcode">Home Team Sport Code</a>

`home_sport_code` is the home team's sport code. It has the following value:

+ `mlb`

### <a name="bhomeid">Home Team ID</a>

`home_id` is the ID number used for the home team.

### <a name="bhomecode">Home Team Code</a>

`home_team_code` is the team code for the home team.

### <a name="bhomefullname">Home Team Full Name</a>

`home_fname` is the home team's full name.

### <a name="bhomeshortname">Home Team Short Name</a>

`home_sname` is the home team's short name.

### <a name="bhomewins">Home Team Wins</a>

`home_wins` is the home team's total wins **including** the game in question.

### <a name="bhomelosses">Home Team Losses</a>

`home_loss` is the home team's total losses **including** the game in question.

## <a name="elinescore">Linescore Element</a>

The `<linescore>` element describes scoring information.

    <linescore away_team_runs="4" home_team_runs="5" away_team_hits="5" home_team_hits="10" away_team_errors="0" home_team_errors="0">

### Linescore Attributes

+ [Away Team Runs](#lawayruns)
+ [Away Team Hits](#lawayhits)
+ [Away Team Errors](#lawayerrors)
+ [Home Team Runs](#lhomeruns)
+ [Home Team Hits](#lhomehits)
+ [Home Team Errors](#lhomeerrors)
+ [Note](#lnote)

#### <a name="lawayruns">Away Team Runs</a>

`away_team_runs` is the total number of runs for the away team.

#### <a name="lawayhits">Away Team Hits</a>

`away_team_hits` is the total number of hits for the away team.

#### <a name="lawayerrors">Away Team Errors</a>

`away_team_errors` is the total number of errors for the away team.

#### <a name="lhomeruns">Home Team Runs</a>

`home_team_runs` is the total number of runs for the home team.

#### <a name="lhomehits">Home Team Hits</a>

`home_team_hits` is the total number of hits for the home team.

#### <a name="lhomeerrors">Home Team Errors</a>

`home_team_errors` is the total number of errors for the home team.

#### <a name="lnote">Note</a>

`note` is game description when winning run scored. It is present when the game is won in the bottom of the final inning.

### <a name="einninglinescore">Inning Line Score Element</a>

`<inning_line_score/>` element describes a single inning's scoring.

    <inning_line_score away="0" home="2" inning="3"/>

#### Inning Line Score Attributes

+ [Away](#iaway)
+ [Home](#ihome)
+ [Inning](#iinning)

#### <a name="iaway">Away</a>

`away` is the total number of runs for the away team.

#### <a name="ihome">Home</a>

`home` is the total number of runs for the home team. If the home team does not need to bat in the bottom of the final inning, the value is `x`.

#### <a name="iinning">Inning</a>

`inning` is the inning number.

### <a name="epitching">Pitching Element</a>

The `<pitching>` element describes pitching statistics for a single team.

    <pitching team_flag="home" out="27" h="5" r="4" er="4" bb="4" so="13" hr="2" bf="36" era="3.50">

#### Pitching Attributes

+ [Team Flag](#pteamflag)
+ [Batters Faced](#pbattersfaced)
+ [Hits](#phits)
+ [Runs](#pruns)
+ [Home Runs](#phomeruns)
+ [Strike Outs](#pstrikeouts)
+ [Walks](#pwalks)
+ [Outs](#pouts)
+ [Earned Runs](#pearnedruns)
+ [Earned Run Average](#pearnedrunaverage)

#### <a name="pteamflag">Team Flag</a>

`team_flag` identifies if the team is home or away. It has of the following values:

+ `away`
+ `home`

#### <a name="pbattersfaced">Batters Faced</a>

`bf` is the total number of batters faced by the pitching staff.

#### <a name="phits">Hits</a>

`h` is the total number of hits allowed by the pitching staff.

#### <a name="pruns">Runs</a>

`r` is the total number of runs allowed by the pitching staff.

#### <a name="phomeruns">Home Runs</a>

`hr` is the total number of home runs allowed by the pitching staff.

#### <a name="pstrikeouts">Strike Outs</a>

`so` is the total number of strike outs by the pitching staff.

#### <a name="pwalks">Walks</a>

`bb` is the total number of walks allowed by the pitching staff.

#### <a name="pouts">Outs</a>

`out` is the total number of outs by the pitching staff.

#### <a name="pearnedruns">Earned Runs</a>

`er` is the total number of earned runs allowed by the pitching staff.

#### <a name="pearnedrunaverage">Earned Run Average</a>

`era` is the earned run average of the pitching staff, [presumably], season to date.

### <a name="epitcher">Pitcher Element</a>

The `<pitcher/>` element describes pitching statistics for a single pitcher.

    <pitcher id="121250" name="Rivera" name_display_first_last="Mariano Rivera" pos="P" out="3" bf="3" er="0" r="0" h="0" so="1" hr="0" bb="0" np="11" s="7" w="1" l="1" sv="22" bs="4" hld="0" s_ip="34.0" s_h="29" s_r="7" s_er="7" s_bb="5" s_so="29" era="1.85" save="true" note="(S, 22)"/>

#### Pitcher Attributes

+ [ID](#piid)
+ [Name](#piname)
+ [Display Name](#pinamedisplay)
+ [Position](#piposition)
+ [Batters Faced](#pibattersfaced)
+ [Number of Pitches](#pinumberpitches)
+ [Strikes](#pistrikes)
+ [Hits](#pihits)
+ [Runs](#piruns)
+ [Home Runs](#pihomeruns)
+ [Strike Outs](#pistrikeouts)
+ [Walks](#piwalks)
+ [Outs](#piouts)
+ [Earned Runs](#piearnedruns)
+ [Won](#piwon)
+ [Lost](#pilost)
+ [Saved](#pisaved)
+ [Blew Save](#piblewsave)
+ [Note](#pinote)
+ [Earned Run Average](#piearnedrunaverage)
+ [Wins](#piwins)
+ [Losses](#pilosses)
+ [Holds](#piholds)
+ [Saves](#pisaves)
+ [Blown Saves](#piblownsaves)
+ [Season Innings Pitched](#piseasoninningspitched)
+ [Season Hits](#piseasonhits)
+ [Season Runs](#piseasonruns)
+ [Season Walks](#piseasonwalks)
+ [Season Strike Outs](#piseasonstrikeouts)
+ [Season Earned Runs](#piseasonearnedruns)

#### <a name="piid">ID</a>

`id` is the ID number used for the player

#### <a name="piname">Name</a>

`name` is the player's name. This value may be last name only, last name with first initial, or last name and first name.

#### <a name="pinamedisplay">Display Name</a>

`name_display_first_last` is the player's first and last name.

#### <a name="piposition">Position</a>

`pos` is the player's position. It has one of the following values:

+ `P` -- Pitcher

The following are *uncommon* values (likely from College games):

+ `3B-P`
+ `C-SS-P`
+ `PH-CF-CF-P`
+ `PH-P-DH`
+ `2B-P`
+ `PH-CF-P`
+ `1B-RF-P`
+ `P-RF-P`
+ `RF-P`
+ `SS-P`
+ `CF-P`
+ `DH-P`
+ `PR-DH-P`
+ `C-P`
+ `PH-P`
+ `PH-C-P`
+ `PH-LF-P`
+ `1B-P`
+ `LF-P`
+ `RF-P-RF`

#### <a name="pibattersfaced">Batters Faced</a>

`bf` is the total number of batters faced by the pitcher.

#### <a name="pinumberpitches">Number of Pitches</a>

`np` is the total number of pitches thrown by the pitcher.

#### <a name="pistrikes">Strikes</a>

`s` is the total number of strikes thrown by the pitcher.

#### <a name="pihits">Hits</a>

`h` is the total number of hits allowed by the pitcher.

#### <a name="piruns">Runs</a>

`r` is the total number of runs allowed by the pitcher.

#### <a name="pihomeruns">Home Runs</a>

`hr` is the total number of home runs allowed by the pitcher.

#### <a name="pistrikeouts">Strike Outs</a>

`so` is the total number of strike outs by the pitcher.

#### <a name="piwalks">Walks</a>

`bb` is the total number of walks allowed by the pitcher.

#### <a name="piouts">Outs</a>

`out` is the total number of outs by the pitcher.

#### <a name="piearnedruns">Earned Runs</a>

`er` is the total number of earned runs allowed by the pitcher.

#### <a name="piwon">Won</a>

`win` identifies if the pitcher won the game. If present, it has the following value:

+ `true`

#### <a name="pilost">Lost</a>

`loss` identifies if the pitcher lost the game. If present, it has the following value:

+ `true`

#### <a name="pisaved">Saved</a>

`save` identifies if the pitcher saved the game. If present, it has the following value:

+ `true`

#### <a name="piblewsave">Blew Save</a>

`blown_save` identifies if the pitcher blew the save. If present, it has the following value:

+ `true`

#### <a name="pinote">Note</a>

`note` describes the outcome of the player's appearance. It may not be present.

#### <a name="piearnedrunaverage">Earned Run Average</a>

`era` is the earned run average of the pitcher, presumably for the season to date.

#### <a name="piwins">Wins</a>

`w` is the total number of wins for the pitcher, season to date.

#### <a name="pilosses">Losses</a>

`l` is the total number of losses for the pitcher, season to date.

#### <a name="piholds">Holds</a>

`hld` is the total number of holds for the pitcher, season to date.

#### <a name="pisaves">Saves</a>

`sv` is the total number of saves for the pitcher, season to date.

#### <a name="piblownsaves">Blown Saves</a>

`bs` is the total number of blown saves for the pitcher, season to date.

#### <a name="piseasoninningspitched">Season Innings Pitched</a>

`s_ip` is the total number of innings pitched by the pitcher, season to date.

#### <a name="piseasonhits">Season Hits</a>

`s_h` is the total number of hits allowed by the pitcher, season to date.

#### <a name="piseasonruns">Season Runs</a>

`s_r` is the total number of runs allowed by the pitcher, season to date.

#### <a name="piseasonwalks">Season Walks</a>

`s_bb` is the total number of walks allowed by the pitcher, season to date.

#### <a name="piseasonstrikeouts">Season Strike Outs</a>

`s_so` is the total number of strike outs for the pitcher, season to date.

#### <a name="piseasonearnedruns">Season Earned Runs</a>

`s_er` is the total number of earned runs allowed by the pitcher, season to date.

## <a name="ebatting">Batting Element</a>

The `<batting>` element describes batting statistics for a single team.

    <batting team_flag="home" ab="29" r="5" h="10" d="2" t="0" hr="1" rbi="5" bb="6" po="27" da="9" so="5" lob="20" avg=".259">

### Batting Attributes

+ [Team Flag](#bteamflag)
+ [At Bats](#batbats)
+ [Average](#baverage)
+ [Hits](#bhits)
+ [Walks](#bwalks)
+ [Strike Outs](#bstrikeouts)
+ [Runs](#bruns)
+ [RBI](#brbi)
+ [Left on Base](#blob)
+ [Doubles](#bdoubles)
+ [Triples](#btriples)
+ [Home Runs](#bhomeruns)
+ [Defensive Average](#bdefensiveaverage)
+ [Put Outs](#bputouts)

#### <a name="bteamflag">Team Flag</a>

`team_flag` identifies if the team is home or away. It has one of the following values:

+ `away`
+ `home`

#### <a name="batbats">At Bats</a>

`ab` is the total number of at bats for the team.

#### <a name="baverage">Average</a>

`avg` is the batting average of the team, [presumably]season to date.

#### <a name="bhits">Hits</a>

`h` is the total number of hits for the team.

#### <a name="bwalks">Walks</a>

`bb` is the total number of walks for the team.

#### <a name="bstrikeouts">Strike Outs</a>

`so` is the total number of strike outs for the team.

#### <a name="bruns">Runs</a>

`r` is the total number of runs scored by the team.

#### <a name="brbi">RBI</a>

`rbi` is the total number of RBI for the team.

#### <a name="blob">Left on Base</a>

`lob` is the total number of men left on base for the team.

#### <a name="bdoubles">Doubles</a>

`d` is the total number of doubles for the team.

#### <a name="btriples">Triples</a>

`t` is the total number of triples for the team.

#### <a name="bhomeruns">Home Runs</a>

`hr` is the total number of home runs for the team.

#### <a name="bdefensiveaverage">Defensive Average</a>

`da` is the defensive average for the team.

#### <a name="bputouts">Put Outs</a>

`po` is the total number of put outs for the team.

## <a name="ebatter">Batter Element</a>

The `<batter/>` element describes batting statistics for a single batter.

    <batter id="116539" name="Jeter" name_display_first_last="Derek Jeter" pos="SS" bo="100" ab="5" po="0" r="2" a="2" bb="0" sac="0" t="0" sf="0" h="5" e="0" d="1" hbp="0" so="0" hr="1" rbi="2" lob="0" fldg="1.000" sb="1" cs="1" s_hr="3" s_rbi="24" s_h="77" s_bb="24" s_r="42" s_so="33" avg=".270" ao="0"/>

### Batter Attributes

+ [ID](#baid)
+ [Name](#baname)
+ [Display Name](#badisplayname)
+ [Position](#baposition)
+ [Batting Order](#babattingorder)
+ [At Bats](#baatbats)
+ [Batting Average](#babattingaverage)
+ [Hits](#bahits)
+ [Walks](#bawalks)
+ [Hit By Pitch](#bahitbypitch)
+ [Strike Outs](#bastrikeouts)
+ [Runs](#baruns)
+ [RBI](#barbi)
+ [Left on Base](#balob)
+ [Doubles](#badoubles)
+ [Triples](#batriples)
+ [Home Runs](#bahomeruns)
+ [Sacrifices](#basacrifices)
+ [Sacrifice Flies](#basacrificeflies)
+ [Ground Outs](#bagroundouts)
+ [Fly Outs](#baflyouts)
+ [Ground into Double Play](#bagidp)
+ [Stolen Bases](#bastolenbases)
+ [Caught Stealing](#bacaughtstealing)
+ [Put Outs](#baputouts)
+ [Assists](#baassists)
+ [Errors](#baerrors)
+ [Fielding Percentage](#bafldg)
+ [Note](#banote)
+ [Season Hits](#baseasonhits)
+ [Season Walks](#baseasonwalks)
+ [Season Strike Outs](#baseasonstrikeouts)
+ [Season Runs](#baseasonruns)
+ [Season RBI](#baseasonrbi)
+ [Season Home Runs](#baseasonhomeruns)

#### <a name="baid">ID</a>

`id` is the ID number used for the player.

#### <a name="baname">Name</a>

`name` is the player's name. This value may be last name only, last name with first initial, or last name and first name.

#### <a name="badisplayname">Display Name</a>

`name_display_first_last` is the player's first and last name.

#### <a name="baposition">Position</a>

`pos` is the player's position. It can have one of several values. The value may use one or more of the following in combination:

+ `P` indicates pitcher
+ `C` indicates catcher
+ `1B` indicates first base
+ `2B` indicates second base
+ `3B` indicates third base
+ `SS` indicates shortstop
+ `LF` indicates left field
+ `CF` indicates center field
+ `RF` indicates right field
+ `DH` indicates designated hitter
+ `PH` indicates pinch hitter
+ `PR` indicates pinch runner

#### <a name="babattingorder">Batting Order</a>

`bo` is the batting order position for the batter.

+ `100` -- leadoff
+ `200` -- second batter
+ `300` -- third batter
+ `400` -- fourth batter
+ `500` -- fifth batter
+ `600` -- sixth batter
+ `700` -- seventh batter
+ `800` -- eighth batter
+ `900` -- ninth batter

In addition to starting lineup information, it also provides substitution information.

+ `701` -- first substitution for the seventh batter
+ `904` -- fourth substitution for the ninth batter

#### <a name="baatbats">At Bats</a>

`ab` is the total number of at bats for the batter.

#### <a name="babattingaverage">Batting Average</a>

`avg` is the batting average for the batter, season to date.

#### <a name="bahits">Hits</a>

`h` is the total number of hits for the batter.

#### <a name="bawalks">Walks</a>

`bb` is the total number of walks for the batter.

#### <a name="bahitbypitch">Hit By Pitch</a>

`hbp` is the total number of hit by pitches for the batter.

#### <a name="bastrikeouts">Strike Outs</a>

`so` is the total number of strike outs for the batter.

#### <a name="baruns">Runs</a>

`r` is the total number of runs scored by the batter.

#### <a name="barbi">RBI</a>

`rbi` is the total number of RBI for the batter.

#### <a name="balob">Left on Base</a>

`lob` is the total number of men left on base by the batter.

#### <a name="badoubles">Doubles</a>

`d` is the total number of doubles for the batter.

#### <a name="batriples">Triples</a>

`t` is the total number of triples for the batter.

#### <a name="bahomeruns">Home Runs</a>

`hr` is the total number of home runs for the batter.

#### <a name="basacrifices">Sacrifices</a>

`sac` is the total number of sacrifice bunts by the batter.

#### <a name="basacrificeflies">Sacrifice Flies</a>

`sf` is the total number of sacrifice flies by the batter.

#### <a name="bagroundouts">Ground Outs</a>

`go` is the total number of ground outs by the batter.

#### <a name="baflyouts">Fly Outs</a>

`ao` is the total number of fly outs by the batter.

#### <a name="bagidp">Ground into Double Play</a>

`gidp` is the total number of grounded into double play's for the batter.

#### <a name="bastolenbases">Stolen Bases</a>

`sb` is the total number of stolen bases by the batter.

#### <a name="bacaughtstealing">Caught Stealing</a>

`cs` is the total number of times caught stealing by the batter.

#### <a name="baputouts">Put Outs</a>

`po` is the total number of put outs by the batter.

#### <a name="baassists">Assists</a>

`a` is the total number of assists by the batter.

#### <a name="baerrors">Errors</a>

`e` is the total number of errors committed by the batter.

#### <a name="bafldg">Fielding Percentage</a>

`fldg` is the fielding percentage for the batter.

#### <a name="banote">Note</a>

`<note>` element content. This attribute is not guaranteed to be present. If present, the value is not guaranteed to be a digit or letter. [Presumably], the two will not mix and match (i.e. if there are two or more note attribute instances, they will all be either digits or letters).

`note` element is detailed further down but an example to provide context for the note attribute value as a key can be seen below.

    <note>
        <![CDATA[
            <span>a-Flied out for Jaso in the 7th. b-Struck out for Brignac in the 7th. </span>
        ]]>
    </note>

`<span>` tags, there are two sentences, each preceded by a character and hyphen. `<batter/>` element. Naturally, this content can be parsed using the note attribute value as a "key".

#### <a name="baseasonhits">Season Hits</a>

`s_h` is the total number of hits for the batter, season to date.

#### <a name="baseasonwalks">Season Walks</a>

`s_bb` is the total number of walks for the batter, season to date.

#### <a name="baseasonstrikeouts">Season Strike Outs</a>

`s_so` is the total number of strike outs for the batter, season to date.

#### <a name="baseasonruns">Season Runs</a>

`s_r` is teh total number of runs scored by the batter, season to date.

#### <a name="baseasonrbi">Season RBI</a>

`s_rbi` is the total number of RBI for the batter, season to date.

#### <a name="baseasonhomeruns">Season Home Runs</a>

`s_hr` is the total number of home runs for the batter, season to date.

## <a name="enote">Note Element</a>

The `<batter/>` element's note attribute is a key for the `<note>` element. Please see the [note attribute](#banote) for a complete description of how the two are used together.

    <note>
        <![CDATA[
            <span>a-Flied out for Jaso in the 7th. b-Struck out for Brignac in the 7th. </span>
        ]]>
    </note>

## <a name="etextdata">Text Data Element</a>

The `note` element describes game statistics in a CDATA block (formatting provided for easier viewing).

    <text_data>
        <![CDATA[
            <b>BATTING</b><br/>
            <span><b>3B</b>: Damon (4, Robertson, D).</span><br/>
            <span><b>HR</b>: Joyce (12, 2nd inning off Burnett, AJ, 0 on, 2 out), Upton, B (15, 4th inning off Burnett, AJ, 1 on, 2 out).</span><br/>
            <span><b>TB</b>: Upton, B 4; Damon 3; Joyce 5; Zobrist.</span>
            <br/><span><b>RBI</b>: Joyce (41), Upton, B 2 (50), Zobrist (43).</span><br/>
            <span><b>2-out RBI</b>: Joyce; Upton, B 2.</span><br/>
            <span><b>Runners left in scoring position, 2 out</b>: Rodriguez, S; Zobrist; Joyce 2.</span><br/>
            <span><b>SAC</b>: Brignac.</span><br/>
            <b>Team RISP</b>: 2-for-10.<br/>
            <b>Team LOB</b>: 5.<br/><br/>
            <b>BASERUNNING</b><br/>
            <span><b>SB</b>: Zobrist 2 (10, 2nd base off Burnett, AJ/Martin, R, 2nd base off Robertson, D/Martin, R), Joyce (5, 2nd base off Burnett, AJ/Martin, R), Upton, B (21, 2nd base off Logan/Martin, R).</span><br/><br/>
            <b>FIELDING</b><br/>
            <span><b>DP</b>: 3 (Brignac-Rodriguez, S-Kotchman, Rodriguez, S-Brignac-Kotchman, Shoppach-Rodriguez, S).</span><br/><br/>
        ]]>
    </text_data>

## <a name="egameinfo">Game Info Element</a>

The `<game_info>` element describes game related statistics, umpire information, and attendance numbers among other things. Like the `<note>` and `<text_data>` elements, it is described in a CDATA block (formatting provided for easier viewing).

    <game_info>
        <![CDATA[
            <span><b>IBB</b>: Kotchman (by Robertson, D), Martin, R (by Price).</span><br/>
            <span><b>HBP</b>: Cano (by Price).</span><br/>
            <span><b>Pitches-strikes</b>: Price 112-71, Gomes, B 13-6, Howell 22-11, Peralta, Jo 15-10, Burnett, AJ 89-51, Logan 9-6, Wade 8-5,Robertson, D 19-12, Rivera 11-7.</span><br/>
            <span><b>Groundouts-flyouts</b>: Price 7-2, Gomes, B 0-1, Howell 0-0, Peralta, Jo 2-0, Burnett, AJ 8-0, Logan 1-0, Wade 0-1, Robertson, D 0-2, Rivera 1-1.</span><br/>
            <span><b>Batters faced</b>: Price 24, Gomes, B 4, Howell 5, Peralta, Jo 5, Burnett, AJ 23, Logan 2, Wade 2, Robertson, D 6, Rivera 3.</span><br/>
            <span><b>Inherited runners-scored</b>: Howell 2-0, Peralta, Jo 2-0, Logan 1-0.</span><br/>
            <b>Umpires</b>: HP: Jim Wolf. 1B: Ron Kulpa. 2B: Gary Cederstrom. 3B: Derryl Cousins. <br/>
            <b>Weather</b>: 84 degrees, sunny.<br/>
            <b>Wind</b>: 8 mph, Out to RF.<br/>
            <b>T</b>: 3:09.<br/>
            <b>Att</b>: 48,103.<br/>
            <b>Venue</b>: Yankee Stadium.<br/>
            <b>July 9, 2011</b><br/>
        ]]>
    </game_info>
