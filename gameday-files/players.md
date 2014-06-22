# players.xml

The players.xml file provides information about game participants. It consists of the following elements.

+ [`<game>`](#egame)
+ [`<team>`](#eteam)
+ [`<player>`](#eplayer)
+ [`<coach>`](#ecoach)
+ [`<umpires>`](#eumpires)
+ [`<umpire>`](#eumpire)

These elements form the following structure:

    <game>
        <team>
            <player/> # multiple elements
            <coach/> # multiple elements
        </team>
        <team>
            <player/> # multiple elements
            <coach/> # multiple elements
        </team>
        <umpires>
            <umpire/> # multiple elements
        </umpire>
    </game>

## <a name="egame">Game Element</a>

The `<game>` element describes basic game information.

    <game venue="Yankee Stadium" date="July 9, 2011">

### Game Attributes

+ [Date](#gdate)
+ [Venue](#gvenue)

#### <a name="gdate">Date</a>

`date` is the date of the game.

#### <a name="gvenue">Venue</a>

`venue` is the venue's name

## <a name="eteam">Team Element</a>

The `<team>` element describes basic team information.

    <team type="home" id="NYY" name="New York Yankees">

### Team Attributes

+ [ID](#tid)
+ [Name](#tname)
+ [Type](#ttype)

#### <a name="tid">ID</a>

`id` is an identifier for the team. It's value is the team's abbreviation which can be seen [here](./team-information.md).

#### <a name="tname">Name</a>

`name` is the team's full name. It's value is the team's full name which can be seen [here](./team-information.md).

#### <a name="ttype">Type</a>

`type` identifies the home and away team. It has one of two values:

+ `away`
+ `home`

## <a name="eplayer">Player Element</a>

The `<player/>` element describes a single player.

    <player id="116539" first="Derek" last="Jeter" num="2" boxname="Jeter" rl="R" bats="R" position="SS" current_position="SS" status="A" team_abbrev="NYY" team_id="147" parent_team_abbrev="NYY" parent_team_id="147" bat_order="1" game_position="SS" avg=".257" hr="2" rbi="22"/>

### Player Attributes

+ [ID](#pid)
+ [First Name](#pfirstname)
+ [Last Name](#plastname)
+ [Number](#pnumber)
+ [Boxname](#pboxname)
+ [Throws](#pthrows)
+ [Bats](#pbats)
+ [Position](#pposition)
+ [Current Position](#pcurrentposition)
+ [Status](#pstatus)
+ [Team Abbreviation](#pteamabbreviation)
+ [Team ID](#pteamid)
+ [Parent Team Abbreviation](#pparentteamabbreviation)
+ [Parent Team ID](#pparentteamid)
+ [Batting Order](#pbattingorder)
+ [Game Position](#pgameposition)
+ [Batting Average](#pavg)
+ [Home Runs](#phr)
+ [RBI](#prbi)

#### <a name="pid">ID</a>

`id` is the ID number used for the player.

#### <a name="pfirstname">First Name</a>

`first` is the player's first name.

#### <a name="plastname">Last Name</a>

`last` is the player's last name.

#### <a name="pnumber">Number</a>

`num` is the player's number.

#### <a name="pboxname">Boxname</a>

`boxname` is the player's box score name.

#### <a name="pthrows">Throws</a>

`rl` identifies which arm the player throws with. It has one of two common values:

+ `R` -- right
+ `L` -- left

The following is an *uncommon* value

+ `""` -- An empty string with no value

#### <a name="pbats">Bats</a>

`bats` identifies which side of the plate the player hits from. It has one of three values:

+ `R` -- right
+ `L` -- left
+ `S` -- switch

#### <a name="pposition">Position</a>

`position` is the player's main position. The following are common values:

+ `P` -- Pitcher
+ `C` -- Catcher
+ `1B` -- First Base
+ `2B` -- Second Base
+ `3B` -- Third Base
+ `SS` -- Shortstop
+ `LF` -- Left Field
+ `CF` -- Center Field
+ `RF` -- Right Field
+ `D` -- Designated Hitter

The following are *uncommon* values:

+ `O` -- Outfielder
+ `I` -- Infielder
+ `U` -- Utility
+ `S` -- Typo for SS
+ `""` -- An empty string with no value

#### <a name="pcurrentposition">Current Position</a>

`current_position` is the player's current position.

#### <a name="pstatus">Status</a>

`status` identifies the player's status. It has one of the following values:

+ `A` -- Active
+ `D7` -- 7 Day Disabled List
+ `D15` -- 15 Day Disabled List
+ `D60` -- 60 Day Disabled List
+ `DES` -- Designated for Assignment
+ `NRI` -- Non-Roster Invitee
+ `RST` -- Restricted
+ `MIN` -- Minor Leaguer
+ `RM` -- Unknown
+ `TI` -- Unknown
+ `SU` -- Unknown (Suspended?)
+ `""` -- An empty string with no value


#### <a name="pteamabbreviation">Team Abbreviation</a>

`team_abbrev` is the abbreviation for the player's team.

#### <a name="pteamid">Team ID</a>

`team_id` is the ID number used for the player's team.

#### <a name="pparentteamabbreviation">Parent Team Abbreviation</a>

`parent_team_abbrev` is the abbreviation for the parent club of the player's team. Generally, this value is an empty string because a Major League team does **not** have a parent club. However, if present, the value will reflect the team's abbreviation.

#### <a name="pparentteamid">Parent Team ID</a>

`parent_team_id` is the ID number used for the parent club of the player's team. Generally, this value is an empty string because a Major League team does **not** have a parent club. However, if present, the value will reflect the team's ID.

#### <a name="pbattingorder">Batting Order</a>

`bat_order` is the batting order for the player. It has a value of 0-9 where 0 represents a pitcher who is not batting. The values 1-9 represent the traditional batting order positions.

#### <a name="pgameposition">Game Position</a>

`game_position` is the player's position to start the game.

#### <a name="pavg">Batting Average</a>

`avg` is the player's batting average season to date, **not** including the game in question.

#### <a name="phr">Home Runs</a>

`hr` is the player's home run total season to date, **not** including the game in question.

#### <a name="prbi">RBI</a>

`rbi` is the player's RBI total season to date, **not** including the game in question.

## <a name="ecoach">Coach Element</a>

The `<coach/>` element describes a single coach.

    <coach position="manager" first="Joe" last="Girardi" id="114833" num="28"/>

### Coach Attributes

+ [ID](#cid)
+ [First](#cfirst)
+ [Last](#clast)
+ [Number](#cnumber)
+ [Position](#cposition)

#### <a name="cid">ID</a>

`id` is the ID number used for the coach.

#### <a name="cfirst">First</a>

`first` is the coach's first name.

#### <a name="clast">Last</a>

`last` is the coach's last name.

#### <a name="cnumber">Number</a>

`num` is the coach's number.

#### <a name="cposition">Position</a>

`position` is the coach's position. It has one of the following values:

+ `manager`
+ `interim_manager`
+ `coach`
+ `bench_coach`
+ `first_base_coach`
+ `third_base_coach`
+ `hitting_coach`
+ `batting_coach`
+ `assistant_hitting_coach`
+ `pitching_coach`
+ `assistant_pitching_coach`
+ `catching_coach`
+ `infield_coach`
+ `bullpen_coach`
+ `major_league_coach`
+ `bench/catching_coach`
+ `quality_assurance_coach`
+ `major_league_assistant_hitting_coach`
+ `catching_and_advance_scouting_coordinator`
+ `bullpen_coordinator`
+ `bullpen_assistant`
+ `bullpen_catcher`
+ `senior_baseball_advisor`
+ `special_advisor`
+ `special_assistant`

## <a name="eumpires">Umpires Element</a>

The `<umpires>` element is a container element that does not have any attributes.

## <a name="eumpire">Umpire Element</a>

The `<umpire/>` element describes a single umpire.

    <umpire position="home" name="Jim Wolf" id="427554"/>

### Umpire Attributes

+ [ID](#uid)
+ [Name](#uname)
+ [Position](#uposition)

#### <a name="uid">ID</a>

`id` is the ID number used for the umpire.

#### <a name="uname">Name</a>

`name` is the name of the umpire.

#### <a name="uposition">Position</a>

`position` is the umpire's position. It has one of the following values:

+ `home` -- Home Plate
+ `first` -- First Base
+ `second` -- Second Base
+ `third` -- Third Base
+ `left` -- Left Field
+ `right` -- Right Field
