# benchO.xml

The benchO.xml file provides information about the bench players *after* the game has completed. The `O` stands for official. It consists of the following elements:

+ [`<bench>`](#ebench)
+ [`<away>`](#eaway)
+ [`<home>`](#ehome)
+ [`<batters>`](#ebatters)
+ [`<pitchers>`](#epitchers)
+ [`<batter/>`](#ebatter)
+ [`<pitcher/>`](#epitcher)

These elements form the following structure:

    <bench>
        <away>
            <batters>
                <batter/> # multiple elements
            </batters>
            <pitchers>
                <pitcher/> # multiple elements
            </pitchers>
        </away>
        <home>
            <batters>
                <batter/> # multiple elements
            </batters>
            <pitchers>
                <pitcher/> # multiple elements
            </pitchers>
        </home>

## <a name="ebench">Bench Element</a>

The `<bench>` element is a container element that does not have any attributes.

## <a name="eaway">Away Element</a>

The `<away>` element describes the away team.

    <away tid="tba" name="Tampa Bay">

### Away Attributes

+ [Team ID](#atid)
+ [Name](#aname)

#### <a name="atid">Team ID</a>

`tid` is a three-letter identifer. It is the same value as the team's `code` attribute seen [here](./team-information.md).

#### <a name="aname">Name</a>

`name` is the away team's city name.

## <a name="ehome">Home Element</a>

The `<home>` element describes the home team.

    <home tid="nya" name="New York">


### Home Attributes

+ [Team ID](#htid)
+ [Name](#hname)

#### <a name="htid">Team ID</a>

`tid` is a three-letter identifer. It is the same value as the team's `code` attribute seen [here](./team-information.md).

#### <a name="hname">Name</a>

`name` is the home team's city name.

## <a name="ebatters">Batters Element</a>

The `<batters>` element is a container element that does not have any attributes.

## <a name="ebatter">Batter Element</a>

    <batter id="430897" last="Swisher" b="S" pos="RF" avg=".249" g="82" ab="281" r="41" h="70" hr="10" rbi="49" sb="2"/>

### Batter Attributes

+ [ID](#bid)
+ [Last](#blast)
+ [Position](#bpos)
+ [Bats](#bbats)
+ [Games](#bgames)
+ [At Bats](#batbats)
+ [Batting Average](#bbattingaverage)
+ [Hits](#bhits)
+ [Runs](#bruns)
+ [RBI](#brbi)
+ [Home Runs](#bhomeruns)
+ [Stolen Bases](#bstolenbases)

#### <a name="bid">ID</a>

`id` is the ID number used for the player.

#### <a name="blast">Last</a>

`last` is the player's last name.

#### <a name="bpos">Position</a>

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
+ `IF` -- Infielder
+ `OF` -- Outfielder
+ `--` -- No value

#### <a name="bbats">Bats</a>

`b` identifies which side of the plate the player hits from. It has one of the following values:

+ `R` -- Right
+ `L` -- Left
+ `S` -- Switch

#### <a name="bgames">Games</a>

`g` is the total number of games the player has appeared in, season to date.

#### <a name="batbats">At Bats</a>

`ab` is the total number of at bats for the player, season to date.

#### <a name="bbattingaverage">Batting Average</a>

`avg` is the batting average for the player, season to date.

#### <a name="bhits">Hits</a>

`h` is the total number of hits for the player, season to date.

#### <a name="bruns">Runs</a>

`r` is the total number of runs scored by the player, season to date.

#### <a name="brbi">RBI</a>

`rbi` is the total number of RBI for the player, season to date.

#### <a name="bhomeruns">Home Runs</a>

`hr` is the total home runs for the player, season to date.

#### <a name="bstolenbases">Stolen Bases</a>

`sb` is the total number of stolen bases by the player, season to date.

## <a name="epitchers">Pitchers Element</a>

The `<pitchers>` element is a container element that does not have any attributes.

## <a name="epitcher">Pitcher Element</a>

    <pitcher id="282332" last="Sabathia" t="L" w="12" l="4" era="2.90" g="19" sv="0" ip="136.2" h="130" bb="34" so="117"/>

### Pitcher Attributes

+ [ID](#pid)
+ [Last](#plast)
+ [Throws](#pthrows)
+ [Games](#pgames)
+ [Innings Pitched](#pinningspitched)
+ [Hits](#phits)
+ [Walks](#pwalks)
+ [Strike Outs](#pstrikeouts)
+ [Wins](#pwins)
+ [Losses](#plosses)
+ [Saves](#psaves)
+ [ERA](#pera)

#### <a name="pid">ID</a>

`id` is the ID number used for the player.

#### <a name="plast">Last</a>

`last` is the player's last name.

#### <a name="pthrows">Throws</a>

`t` identifies which arm the player throws with. It has one of the following values:

+ `R` -- Right
+ `L` -- Left
+ `""` -- Empty string value

#### <a name="pgames">Games</a>

`g` is the total number of games the player has appeared in, season to date.

#### <a name="pinningspitched">Innings Pitched</a>

`ip` is the total number of innings pitched, season to date.

#### <a name="phits">Hits</a>

`h` is the total number of hits allowed, season to date.

#### <a name="pwalks">Walks</a>

`bb` is the total number of walks allowed, season to date.

#### <a name="pstrikeouts">Strike Outs</a>

`so` is the total number of strike outs for the player, season to date.

#### <a name="pwins">Wins</a>

`w` is the total number of wins for the player, season to date.

#### <a name="plosses">Losses</a>

`l` is the total number of losses for the player, season to date.

#### <a name="psaves">Saves</a>

`sv` is the total number of saves for the player, season to date

#### <a name="pera">ERA</a>

`era` is the ERA for the player, season to date.
