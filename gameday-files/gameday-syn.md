# gameday_Syn.xml

The gameday_Syn.xml file provides game information for syndication. It consists of the following elements:

+ [`<mlb-gde>`](#emlbgde)
+ [`<game>`](#egame)
+ [`<date>`](#edate)
+ [`<venue>`](#evenue)
+ [`<game-status>`](#egamestatus)
+ [`<away-team>`](#eawayteam)
+ [`<home-team>`](#ehometeam)
+ [`<lineup>`](#elineup)
+ [`<batter>`](#ebatter)
+ [`<pitcher>`](#epitcher)
+ [`<pitching>`](#epitching)
+ [`<stats>`](#estats)
+ [`<era>`](#eera)
+ [`<w>`](#ewins)
+ [`<l>`](#elosses)
+ [`<sv>`](#esaves)
+ [`<batting>`](#ebatting)
+ [`<atbat>`](#eatbats)
+ [`<avg>`](#eavg)
+ [`<hr>`](#ehomerun)
+ [`<rbi>`](#erbi)
+ [`<sb>`](#estolenbases)
+ [`<on-deck>`](#eondeck)
+ [`<in-hole>`](#einhole)
+ [`<baserunner>`](#ebaserunner)
+ [`<atbat-pitch-by-pitch>`](#eatbatpitchbypitch)
+ [`<pitcher-pitch-count>`](#epitcherpitchcount)
+ [`<pitch>`](#epitch)
+ [`<linescore>`](#elinescore)
+ [`<score>`](#escore)
+ [`<r>`](#eruns)
+ [`<h>`](#ehits)
+ [`<e>`](#eerrors)
+ [`<play-by-play>`](#eplaybyplay)
+ [`<pbp>`](#eplaybyplayitem)
+ [`<pitch-by-pitch>`](#epitchbypitch)
+ [`<scoring-summary>`](#escoringsummary)
+ [`<pickoff-attempt>`](#epickoffattempt)

These elements for the following structure:

    <mlb-gde>
        <game>
            <date></date>
            <venue/>
            <game-status/>
            <away-team/>
            <home-team/>
            <lineup>
                <batter/> # multiple elements
                <pitcher/>
            </lineup>
            <lineup>
                <batter/> # multiple elements
                <pitcher/>
            </lineup>
            <pitching>
                <stats>
                    <era/>
                    <w/>
                    <l/>
                    <sv/>
                </stats>
            </pitching>
            <batting>
                <atbat/> # multiple elements
                <stats>
                    <avg/>
                    <hr/>
                    <rbi/>
                    <sb/>
                </stats>
            </batting>
            <on-deck/>
            <in-hole/>
            <baserunner/>
            <baserunner/>
            <baserunner/>
            <atbat/>
            <atbat-pitch-by-pitch>
                <pitcher-pitch-count/>
                <pickoff-attempt/> # If present, may precede or follow <pitch/> element (may be multiples)
                <pitch/> # multiple elements
            </atbat-pitch-by-pitch/>
            <linescore>
                <score/> # multiple elements
                <r/>
                <h/>
                <e/>
            </linescore>
            <play-by-play> # multiple elements (1 for each half inning)
                <pbp> # multiple elements
            <play-by-play>
            <pitch-by-pitch> # multiple elements (1 for each half inning)
                <atbat> # multiple elements (1 for each batter in the half inning)
                    <pickoff-attempt/> # If present, may precede or follow <pitch/> element (may be multiples)
                    <pitch/> # (possible) multiple elements
                </atbat>
            </pitch-by-pitch>
            <scoring-summary> # (possible) multiple elements (1 for each half inning with a score)
                <score> # (possible) multiple elements (1 for each scoring play)
            </scoring-summary>
        </game>
    </mlb-gde>

## <a name="emlbgde"> MLB Gameday Element</a>

The `<mlb-gde>` element describes MLB Gameday information.

    <mlb-gde version="1.0">

### MLB Gameday Attribtues

+ [Version](#mlbversion)

#### <a name="mlbversion">Version</a>

`version` is the MLB Gameday version number. It has the following value:

+ `1.0`

## <a name="egame">Game Element</a>

The `<game>` element describes basic game information.

    <game id="2011/07/09/tbamlb-nyamlb-1" idpk="288258" status="rebuild">

#### Game Attributes

+ [ID](#gid)
+ [Primary Key](#gidpk)
+ [Status](#gstatus)

#### <a name="gid">ID</a>

`id` is a unique identifier for the game.

#### <a name="gidpk">Primary Key</a>

`idpk` is the game's primary key, [presumably] for the MLB database.

#### <a name="gstatus">Status</a>

`status` is unknown. It appears to have the following value:

+ `rebuild`

## <a name="edate">Date Element</a>

The `date` element describes the date of the game. It does not have any attributes. The content is in the format `YYYY-MM-DD`.

    <date>2011-07-09</date>

## <a name="evenue">Venue Element</a>

The `venue` element provides venue information.

    <venue id="3313" name="Yankee Stadium" location="Bronx"/>

### Venue Attributes

+ [ID](#vid)
+ [Name](#vname)
+ [Location](#vlocation)

#### <a name="vid">ID</a>

`id` is the ID number used for the venue.

#### <a name="vname">Name</a>

`name` is the venue's name.

#### <a name="vlocation">Location</a>

`location` is the venue's location.

## <a name="egamestatus">Game Status Element</a>

The `<game-status>` element describes the game status.

    <game-status status="Final"/>

### Game Status Attributes

+ [Status](#gsstatus)
+ [Delay Reason](#gsdelayreason)

#### <a name="gsstatus">Status</a>

`status` is the game's status. It has one of the following values:

+ `Final`
+ `Completed Early`
+ `Postponed`
+ `Game Over`

#### <a name="gsdelayreason">Delay Reason</a>

`delay_reason` is the reason for the game delay. It has one of the following values:

+ `Tied`
+ `Rain`
+ `Snow`
+ `Other`

## <a name="eawayteam">Away Team Element</a>

The `away-team` element describes the away team.

    <away-team team="tba" name="Rays" city="Tampa Bay" w="49" l="40"/>

### Away Team Attributes

+ [Team](#ateam)
+ [Name](#aname)
+ [City](#acity)
+ [Wins](#awins)
+ [Losses](#alosses)

#### <a name="ateam">Team</a>

`team` is the three-letter identifer used for the away team. See all team codes [here](./team-information).

#### <a name="aname">Name</a>

`name` is the away team's nickname.

#### <a name="acity">City</a>

`city` is the away team's city. If the city is home to multiple teams, this value is the team's name as seen [here](./team-information).

#### <a name="awins">Wins</a>

`w` is the total number of wins for the away team.

#### <a name="alosses">Losses</a>

`l` is the total number of losses for the away team.

## <a name="ehometeam">Home Team Element</a>

The `home-team` element describes the home team.

    <home-team team="nya" name="Yankees" city="NY Yankees" w="52" l="35"/>

### Home Team Attributes

+ [Team](#hteam)
+ [Name](#hname)
+ [City](#hcity)
+ [Wins](#hwins)
+ [Losses](#hlosses)

#### <a name="hteam">Team</a>

`team` is the three-letter identifer used for the home team. See all team codes [here](./team-information).

#### <a name="hname">Name</a>

`name` is the home team's nickname.

#### <a name="hcity">City</a>

`city` is the home team's city. If the city is home to multiple teams, this value is the team's name as seen [here](./team-information).

#### <a name="hwins">Wins</a>

`w` is the total number of wins for the home team.

#### <a name="hlosses">Losses</a>

`l` is the total number of losses for the home team.

## <a name="elineup">Lineup Element</a>

The `lineup` element describes a single lineup as it existed at the *end* of the game.

    <lineup team="nya">

### Lineup Attributes

+ [Team](#lteam)

#### <a name="lteam">Team</a>

`team` is the three-letter team code for the team. See all team codes [here](./team-information).

## <a name="ebatter">Batter Element</a>

The `<batter/>` element describes a single batter in the lineup.

    <batter pid="116539" position="SS" batting_order="1"/>

### Batter Attributes

+ [ID](#bapid)
+ [Position](#baposition)
+ [Batting Order](#babattingorder)

#### <a name="bapid">ID</a>

`pid` is the ID number used for the player.

#### <a name="baposition">Position</a>

`position` is the player's position. It has one of the following values:

+ `P` -- Pitcher
+ `C` -- Catcher
+ `1B` -- First Base
+ `2B` -- Second Base
+ `3B` -- Third Base
+ `SS` -- Shortstop
+ `LF` -- Left Field
+ `CF` -- Center Field
+ `RF` -- Right Field
+ `DH` -- Designated Hitter
+ `PH` -- Pinch Hitter
+ `PR` -- Pinch Runner

#### <a name="babattingorder">Batting Order</a>

`batting_order` identifies which lineup spot the player holds. It has one of the following values:

+ `1`
+ `2`
+ `3`
+ `4`
+ `5`
+ `6`
+ `7`
+ `8`
+ `9`

## <a name="epitcher">Pitcher Element</a>

The `<pitcher/>` describes a single pitcher.

    <pitcher pid="121250"/>

### Pitcher Attributes

+ [ID](#piid)

#### <a name="piid">ID</a>

`pid` is the ID number used for the player.

## <a name="epitching">Pitching Element</a>

The `<pitching>` element describes the final pitcher fo a single team.

    <pitching team="nya" pid="121250" throws="R" bats="R" ip="1.0" so="1" h="0" r="0" er="0" bb="0">

### Pitching Attributes

+ [Team](#pitteam)
+ [ID](#pitid)
+ [Throws](#pitthrows)
+ [Bats](#pitbats)
+ [Innings Pitched](#pitinningspitched)
+ [Strike Outs](#pitstrikeouts)
+ [Hits](#pithits)
+ [Walks](#pitwalks)
+ [Runs](#pitruns)
+ [Earned Runs](#pitearnedruns)

#### <a name="pitteam">Team</a>

`team` is the three-letter team code for the team. See all team codes [here](./team-information).

#### <a name="pitid">ID</a>

`pid` is the ID number used for the player.

#### <a name="pitthrows">Throws</a>

`throws` identifies which arm the pitcher throws with. It has one of the following values:

+ `R` -- Right
+ `L` -- Left

#### <a name="pitbats">Bats</a>

`bats` identifies which side of the plate the player hits from. It has one of the following values:

+ `R` -- Right
+ `L` -- Left
+ `S` -- Switch

#### <a name="pitinningspitched">Innings Pitched</a>

`ip` is the total number of innings pitched by the player.

#### <a name="pitstrikeouts">Strike Outs</a>

`so` is the total number of strike outs by the player.

#### <a name="pithits">Hits</a>

`h` is the total number of hits allowed by the player.

#### <a name="pitwalks">Walks</a>

`bb` is the total number of walks allowed by the player.

#### <a name="pitruns">Runs</a>

`r` is the total number of runs allowed by the player.

#### <a name="pitearnedruns">Earned Runs</a>

`er` is the total number of earned runs allowed by the player.

## <a name="estats">Stats Element</a>

The `<stats>` element is a container element that does not have any attributes.

## <a name="eera">ERA Element</a>

The `<era/>` element describes the player's ERA.

    <era season="1.85" career="2.22"/>

### ERA Attributes

+ [Season](#eraseason)
+ [Career](#eracareer)

#### <a name="eraseason">Season</a>

`season` is the player's ERA for the season.

#### <a name="eracareer">Career</a>

`career` is the player's ERA for their career.

## <a name="ewins">Wins Element</a>

The `w` element describes the player's wins.

    <w season="1" career="75"/>

#### Wins Attributes

+ [Season](#winsseason)
+ [Career](#winscareer)

#### <a name="winsseason">Season</a>

`season` is the player's win total for the season.

#### <a name="winscareer">Career</a>

`career` is the player's win total for their career.

## <a name="elosses">Loss Element</a>

    <l season="1" career="56"/>

The `l` element describes the player's losses.

#### Losses Attributes

+ [Season](#lossesseason)
+ [Career](#lossescareer)

#### <a name="lossesseason">Season</a>

`season` is the player's loss total for the season.

#### <a name="lossescareer">Career</a>

`career` is the player's loss total for their career.

## <a name="esaves">Save Element</a>

The `sv` element describes the player's saves.

    <sv season="22" career="581"/>

#### Saves Attributes

+ [Season](#savesseason)
+ [Career](#savescareer)

#### <a name="savesseason">Season</a>

`season` is the player's saves total for the season.

#### <a name="savescareer">Career</a>

`career` is the player's saves total for their career.

## <a name="ebatting">Batting Element</a>

The `<batting>` element describes the final player to bat in the game.

    <batting team="tba" pid="448605" throws="R" bats="R" position="LF" ab="2" r="0" h="0" rbi="0">

#### Batting Attributes

+ [Team](#batteam)
+ [ID](#batpid)
+ [Throws](#batthrows)
+ [Bats](#batbats)
+ [Position](#batposition)
+ [At Bats](#batatbats)
+ [Runs](#batruns)
+ [Hits](#bathits)
+ [RBI](#batrbi)

#### <a name="batteam">Team</a>

`team` is the three-letter team code for the team. See all team codes [here](./team-information).

#### <a name="batpid">ID</a>

`pid` is the ID number used for the player.

#### <a name="batthrows">Throws</a>

`throws` identifies which arm the pitcher throws with. It has one of the following values:

+ `R` -- Right
+ `L` -- Left

#### <a name="batbats">Bats</a>

`bats` identifies which side of the plate the player hits from. It has one of the following values:

+ `R` -- Right
+ `L` -- Left
+ `S` -- Switch

#### <a name="batposition">Position</a>

`position` is the player's position. It has one of the following values:

+ `P` -- Pitcher
+ `C` -- Catcher
+ `1B` -- First Base
+ `2B` -- Second Base
+ `3B` -- Third Base
+ `SS` -- Shortstop
+ `LF` -- Left Field
+ `CF` -- Center Field
+ `RF` -- Right Field
+ `DH` -- Designated Hitter
+ `PH` -- Pinch Hitter

#### <a name="batatbats">At Bats</a>

`ab` is the total number of at bats for the player.

#### <a name="batruns">Runs</a>

`r` is the total runs scored by the player.

#### <a name="bathits">Hits</a>

`h` is the total number of hits by the player.

#### <a name="batrbi">RBI</a>

`rbi` is the total number of RBI by the player.

## <a name="eatbats">At Bat Element</a>

The `<atbat/>` element describes a single at bat. It is used in two different places with two different sets of attributes. Both are described below.

1) As a child element of `<batting>`.

    <atbat inning="7" atbat_result="strikeout"/>

Here `<atbat/>` describes a game at bat for the player who made the final out.

### At Bat Attributes

+ [Inning](#atbat1inning)
+ [Result](#atbat1result)

#### <a name="atbat1inning">Inning</a>

`inning` is the inning where the at bat occurred.

#### <a name="atbat1result">Result</a>

`atbat_result` is a description of the outcome. It has one of the following values:

+ `single`
+ `double`
+ `triple`
+ `home_run`
+ `walk`
+ `intent_walk`
+ `hit_by_pitch`
+ `sac_bunt`
+ `sac_fly`
+ `strikeout`
+ `strikeout_double_play`
+ `grounded_into_double_play`
+ `double_play`
+ `triple_play`
+ `bunt_grounder`
+ `bunt_line_drive`
+ `bunt_popup`
+ `line_drive`
+ `ground_ball`
+ `fly_ball`
+ `popup`
+ `force_out`
+ `fielders_choice`
+ `fielders_choice_out`
+ `field_error`
+ `catcher_interf
+ `batter_interference`
+ `fan_interference`

2) As a child element of `<game>`

    <atbat inning="9t" outs="3" end_of_atbat="true" trajectory="ground_ball" hit_position_x="103.41" hit_position_y="173.69" atbat_result="ground_ball" play_by_play="Justin Ruggiano grounds out, third baseman Eduardo Nunez to first baseman Mark Teixeira. "/>

Here `<atbat/>` describes the final at bat of the game.

### At Bat Attributes

+ [Inning](#atbat2inning)
+ [Outs](#atbat2outs)
+ [End of At Bat](#atbat2endofatbat)
+ [Trajectory](#atbat2trajectory)
+ [Hit Position X Coordinate](#atbat2hitpositionx)
+ [Hit Position Y Coordinate](#atbat2hitpositiony)
+ [Result](#atbat2result)
+ [Play By Play](#atbat2playbyplay)

#### <a name="atbat2inning">Inning</a>

`inning` is the half inning in which the final out was made. It is a number suffixed with one of the following modifiers:

+ `t` -- Top
+ `b` -- Bottom

#### <a name="atbat2outs">Outs</a>

`outs` is the total outs for the inning. This value will always be `3`

#### <a name="atbat2endofatbat">End of At Bat</a>

`end_of_atbat` identifies if the at bat is finished. It has the following value:

+ `true`
+ `false` -- Passed Ball, Wild Pitch, Balk, Postponed, Error

#### <a name="atbat2trajectory">Trajectory</a>

`trajectory` describes the path of ball. It has one of the following values:

+ `bunt_grounder`
+ `bunt_popup`
+ `ground_ball`
+ `fly_ball`
+ `line_drive`
+ `popup`

#### <a name="atbat2hitpositionx">Hit Position X Coordinate</a>

`hit_position_x` is the X coordinate position for the ball in play.

#### <a name="atbat2hitpositiony">Hit Position Y Coordinate</a>

`hit_position_y` is the Y coordinate position for the ball in play.

#### <a name="atbat2result">Result</a>

`atbat_result` is a description of the outcome. It has one of the following values:

+ `single`
+ `double`
+ `triple`
+ `home_run`
+ `walk`
+ `hit_by_pitch`
+ `sac_bunt`
+ `sac_fly`
+ `strikeout`
+ `strikeout_double_play`
+ `grounded_into_double_play`
+ `double_play`
+ `bunt_grounder`
+ `bunt_popup`
+ `line_drive`
+ `ground_ball`
+ `fly_ball`
+ `popup`
+ `force_out`
+ `fielders_choice`
+ `fielders_choice_out`
+ `field_error`
+ `batter_interference`

#### <a name="atbat2playbyplay">Play By Play</a>

`play_by_play` is a description of the at bat.

## <a name="eavg">Batting Average Element</a>

The `<avg/>` element describes the player's batting average.

    <avg season=".276" career=".235"/>

### Batting Average Attributes

+ [Season](#battingaverageseason)
+ [Career](#battingaveragecareer)

#### <a name="battingaverageseason">Season</a>

`season` is the player's batting average for the season.

#### <a name="battingaveragecareer">Career</a>

`career` is the player's batting average for their career.

## <a name="ehomerun">Home Run Element</a>

The `<hr/>` element describes the player's home runs.

    <hr season="4" career="6"/>

### Home Runs Attributes

+ [Season](#homerunsseason)
+ [Career](#homerunscareer)

#### <a name="homerunsseason">Season</a>

`season` is the player's home runs for the season.

#### <a name="homerunscareer">Career</a>

`career` is the player's home runs for their career.

## <a name="erbi">RBI Element</a>

The `<rbi/>` element describes the player's RBI.

    <rbi season="13" career="23"/>

### RBI Attributes

+ [Season](#rbiseason)
+ [Career](#rbicareer)

#### <a name="rbiseason">Season</a>

`season` is the player's RBI total for the season.

#### <a name="rbicareer">Career</a>

`career` is the player's RBI total for their career.

## <a name="estolenbases">Stolen Bases Element</a>

The `<sb/>` element describes the player's stolen bases.

    <sb season="1" career="3"/>

### Stolen Bases Attributes

+ [Season](#stolenbasesseason)
+ [Career](#stolenbasescareer)

#### <a name="stolenbasesseason">Season</a>

`season` is the player's RBI total for the season.

#### <a name="stolenbasescareer">Career</a>

`career` is the player's RBI total for their career.

## <a name="eondeck">On Deck Element</a>

The `<on-deck/>` element describes the player on deck when the last out was made.

    <on-deck pid="113028" avg=".279" hr="9" rbi="41"/>

### On Deck Attributes

+ [ID](#odid)
+ [Batting Average](#odbattingaverage)
+ [Home Runs](#odhomeruns)
+ [RBI](#odrbi)

#### <a name="odid">ID</a>

`pid` is the ID number used for the player.

#### <a name="odbattingaverage">Batting Average</a>

`avg` is the player's batting average, season to date.

#### <a name="odhomeruns">Home Runs</a>

`hr` is the total number of home runs for the player, season to date.

#### <a name="odrbi">RBI</a>

`rbi` is the total number of RBI for the player, season to date.

## <a name="einhole">In Hole Element</a>

The `<in-hole/>` element describes the player in the hole when the last out was made.

    <in-hole pid="450314" avg=".272" hr="10" rbi="43"/>

### In Hole Attributes

+ [ID](#ihid)
+ [Batting Average](#ihbattingaverage)
+ [Home Runs](#ihhomeruns)
+ [RBI](#ihrbi)

#### <a name="ihid">ID</a>

`pid` is the ID number used for the player.

#### <a name="ihbattingaverage">Batting Average</a>

`avg` is the player's batting average, season to date.

#### <a name="ihhomeruns">Home Runs</a>

`hr` is the total number of home runs for the player, season to date.

#### <a name="ihrbi">RBI</a>

`rbi` is the total number of RBI for the player, season to date.

## <a name="ebaserunner">Baserunner Element</a>

The `<baserunner/>` describes a baserunner when the last out was made.

    <baserunner base="1" occupied="false"/>

### Baserunner Attributes

+ [ID](#brplayerid)
+ [Base](#brbase)
+ [Occupied](#broccupied)
+ [Stolen Base](#brstolenbase)
+ [Caught Stealing](#brcaughtstealing)
+ [Pitch Result](#brpitchresult)

#### <a name="brplayerid">ID</a>

`id` is the ID number used for the player.

#### <a name="brbase">Base</a>

`base` identifies which base is described. It has one of the following values:

+ `1` -- First Base
+ `2` -- Second Base
+ `3` -- Third Base

#### <a name="broccupied">Occupied</a>

`occupied` identifies if the base is occupied. It has one of the following values:

+ `true`
+ `false`

#### <a name-"brstolenbase">Stolen Bases</a>

`sb` is the total number of stolen bases the player has, season to date. It may not be present.

#### <a name-"brcaughtstealing">Caught Stealing</a>

`cs` is the total number of times the player has been caught stealing, season to date. It may not be present.

#### <a name="brpitchresult">Pitch Result</a>

`pitch_result` is the outcome of the pitch. If present, it has one of the following values:

+ `single`
+ `double`
+ `triple`
+ `walk`
+ `intent_walk`
+ `hit_by_pitch`
+ `sac_bunt`
+ `sac_fly`
+ `strikeout`
+ `force_out`
+ `double_play`
+ `grounded_into_double_play`
+ `fielders_choice`
+ `fielders_choice_out`
+ `field_error`
+ `Pinch Runner`
+ `catcher_interf`
+ `fan_interference`

## <a name="eatbatpitchbypitch">At Bat Pitch By Pitch Element</a>

The `atbat-pitch-by-pitch>` element describes the final at bat pitch by pitch.

    <atbat-pitch-by-pitch balls="0" strikes="0">

### At Bat Pitch By Pitch Attributes

+ [Balls](#abpbpballs)
+ [Strikes](#abpbpstrikes)

#### <a name="abpbpballs">Balls</a>

`balls` is the number of balls in the count inherited by the pitcher.

#### <a name="abpbpstrikes">Strikes</a>

`strikes` is the number of strikes in the count inherited by the pitcher.

## <a name="epitcherpitchcount">Pitcher Pitch Count Element</a>

The `<pitcher-pitch-count/>` element describes pitch count information for the pitcher.

    <pitcher-pitch-count balls="4" strikes="7" total="11"/>

### Pitcher Pitch Count Attributes

+ [Balls](#ppcballs)
+ [Strikes](#ppcstrikes)
+ [Total](#ppctotal)

#### <a name="ppcballs">Balls</a>

`balls` is the total number of balls thrown by the pitcher during their appearance.

#### <a name="ppcstrikes">Strikes</a>

`strikes` is the total number of strikes thrown by the pitcher during their appearance.

#### <a name="ppctotal">Total</a>

`total` is the total number of pitches thrown by the pitcher during their appearance.

## <a name="epitch">Pitch Element</a>

The `<pitch/>` element describes a single pitch. Like the `<atbat/>` element, it is used in two different places with two different sets of attributes. Both are described below.

1) As a child element of `<atbat-pitch-by-pitch>`

    <pitch number="1" x="100.43" y="136.43" pitch="foul"/>

Here `<pitch/>` describes a single pitch in the final at bat of the game.

### Pitch Attributes

+ [Number](#pitch1number)
+ [X Position](#pitch1xposition)
+ [Y Position](#pitch1yposition)
+ [Pitch](#pitch1pitch)

#### <a name="pitch1number">Number</a>

`number` is the pitch number in the at bat.

#### <a name="pitch1xposition">X Position</a>

`x` is the x coordinate position where the pitch crossed the plate.

#### <a name="pitch1yposition">Y Position</a>

`y` is the y coordinate position where the pitch crossed the plate.

#### <a name="pitch1pitch">Pitch</a>

`pitch` is a description of the pitch. It has one of the following values:

+ `ball`
+ `automatic_ball`
+ `called_strike`
+ `swinging_strike`
+ `swinging_strike_blocked`
+ `foul`
+ `foul_tip`
+ `foul_bunt`
+ `missed_bunt`
+ `blocked_ball`
+ `pitchout`
+ `hit_by_pitch`
+ `hit_into_play`
+ `hit_into_play_no_out`
+ `hit_into_play_score`

2) As a child element of `<atbat>` which is a child element of `<pitch-by-pitch>`.

    <pitch number="8" result="hit_into_play_score"/>

Here `<pitch/>` describes a single pitch of an at bat.

### Pitch Attributes

+ [Number](#pitch2number)
+ [Result](#pitch2result)

#### <a name="pitch2number">Number</a>

`number` is the pitch number in the at bat.

#### <a name="pitch2result">Result</a>

`result` is a description of the outcome. It has one of the following values:

<!-- + `called_strike`
+ `swinging_strike`
+ `foul`
+ `ball`
+ `hit_into_play` -->

+ `ball`
+ `automatic_ball`
+ `intent_ball`
+ `called_strike`
+ `automatic_strike`
+ `unknown_strike`
+ `swinging_strike`
+ `swinging_strike_blocked`
+ `foul`
+ `foul_tip`
+ `foul_bunt`
+ `foul_pitchout`
+ `pitchout`
+ `pitchout_hit_into_play`
+ `pitchout_hit_into_play_score`
+ `swinging_pitchout`
+ `blocked_ball`
+ `hit_by_pitch`
+ `hit_into_play`
+ `hit_into_play_no_out`
+ `hit_into_play_score`
+ `missed_bunt`

## <a name="elinescore">Linescore Element</a>

The `<linescore>` element is a container element that does not have any attributes.

## <a name="escore">Score Element</a>

The `<score/>` element describes scoring. It is used in two different places with two different sets of attributes. Both are described below.

1) As a child element of `<linescore>`

    <score inning="8" away="1" home="1"/>

Here `<score/>` describes an inning of scoring.

### Score Attributes

+ [Inning](#scinning)
+ [Away Team Runs](#scaway)
+ [Home Team Runs](#schome)

#### <a name="scinning">Inning</a>

`inning` is the inning number.

#### <a name="scaway">Away Team Runs</a>

`away` is the total runs scored by the away team.

#### <a name="schome">Home Team Runs</a>

`home` is the total runs scored by the home team.

2) As a child element of `<scoring-summary>`

    <score team="nya" description="Derek Jeter homers (3) on a fly ball to left field. " away_score="1" home_score="1"/>

Here `<score/>` describes an individual scoring play.

### Score Attributes

+ [Team](#scorteam)
+ [Description](#scordescription)
+ [Away Team Score](#scorawayteam)
+ [Home Team Score](#scorhometeam)

#### <a name="scorteam">Team</a>

`team` is the three-letter identifer used for the home team. See all team codes [here](./team-information).

#### <a name="scordescription">Description</a>

`description` is description of the scoring play.

#### <a name="scorawayteam">Away Team Score</a>

`away_score` is the away team's score after the play.

#### <a name="scorhometeam">Home Team Score</a>

`home_score` is the home team's score after the play.

## <a name="eruns">Runs Element</a>

The `<r/>` element describes the total runs scored by each team and includes a differential.

    <r away="4" home="5" diff="1"/>

### Runs Attributes

+ [Away Team Runs](#raway)
+ [Home Team Runs](#rhome)
+ [Differential](#rdiff)

#### <a name="raway">Away Team Runs</a>

`away` is the total number of runs scored by the away team.

#### <a name="rhome">Home Team Runs</a>

`home` is the total number of runs scored by the home team.

#### <a name="rdiff">Differential</a>

`diff` is the differential between the team run totals.

## <a name="ehits">Hits Element</a>

The `<h/>` element describes the number of hits for each team.

    <h away="5" home="10"/>

### Hits Attributes

+ [Away Team Hits](#haway)
+ [Home Team Hits](#hhome)

#### <a name="haway">Away Team Hits</a>

`away` is the total number of hits by the away team.

#### <a name="hhome">Home Team Hits</a>

`home` is the total number of hits by the home team.

## <a name="eerrors">Error Element</a>

The `<e/>` element describes the number of errors for each team.

    <e away="0" home="0"/>

### Error Attributes

+ [Away Team Errors](#eraway)
+ [Home Team Errors](#erhome)

#### <a name="eraway">Away Team Errors</a>

`away` is the total number of errors by the away team.

#### <a name="erhome">Home Team Errors</a>

`home` is the total number of errors by the home team.

## <a name="eplaybyplay">Play By Play Element</a>

The `<play-by-play>` element describes the plays for a half inning.

    <play-by-play inning="1t">

### Play By Play Attributes

+ [Inning](#playinning)

#### <a name="playinning">Inning</a>

`inning` is the number inning suffixed with one of the following modifiers:

+ `t` -- Top
+ `b` -- Bottom

## <a name="eplaybyplayitem">Play By Play Item Element</a>

The `<pbp/>` describes a single play.

    <pbp description="Derek Jeter homers (3) on a fly ball to left field. " b="3" s="2" o="1"/>

### Play By Play Item Attributes

+ [Description](#pbpidescription)
+ [Balls](#pbpiballs)
+ [Strikes](#pbpistrikes)
+ [Outs](#pbpiouts)

#### <a name="pbpidescription">Description</a>

`description` is a description of the play.

#### <a name="pbpiballs">Balls</a>

`b` is the number of balls in the count.

#### <a name="pbpistrikes">Strikes</a>

`s` is the number of strikes in the count.

#### <a name="pbpiouts">Outs</a>

`o` is the number of outs in the inning.

## <a name="epitchbypitch">Pitch By Pitch Element</a>

The `<pitch-by-pitch>` element describes the pitches for a half inning.

### Pitch By Pitch Attributes

+ [Inning](#pitchbypitchinning)

#### <a name="pitchbypitchinning">Inning</a>

`inning` is the number inning suffixed with one of the following modifiers:

+ `t` -- Top
+ `b` -- Bottom

## <a name="escoringsummary">Scoring Summary Element</a>

The `<scoring-summary>` element describes the scoring for a half inning.

    <scoring-summary inning="3b">

### Scoring Summary Attributes

+ [Inning](#scoringsummaryinning)

#### <a name="scoringsummaryinning">Inning</a>

`inning` is the number inning suffixed with one of the following modifiers:

+ `t` -- Top
+ `b` -- Bottom

## <a name="epickoffattempt">Pickoff Attempt Element</a>

The `<pickoff-attempt/>` element describes a pickoff attempt by the pitcher. It is seen in two different places with both having the same attribute.

    <pickoff-attempt base="1"/>

### Pickoff Attempt Attributes

+ [Base](#pobase)

#### <a name="pobase">Base</a>

`base` identifies which base the pickoff attempt was made to. It has one of the following values:

+ `1` -- First Base
+ `2` -- Second Base
+ `3` -- Third Base
