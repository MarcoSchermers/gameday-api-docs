# game_events.xml

The game_events.xml file provides information about game events for every at bat. It consists of the following elements:

+ [`<game>`](#egame)
+ [`<inning>`](#einning)
+ [`<top>`](#etop)
+ [`<bottom>`](#ebottom)
+ [`<action/>`](#eaction)
+ [`<atbat>`](#eatbat)
+ [`<pitch/>`](#epitch)
+ [`<atBat/>`](#eatbatfinal)
+ [`<deck/>`](#edeck)
+ [`<hole/>`](#ehole)
 
These elements form the following structure:

	<game>
		<inning> # one or more elements. Equal to the number of innings played.
			<top>
				<action/> # zero or more elements. May precede/succeed an <atbat> element.
				<atbat> # three or more elements. Equal to the number of at bats in the half inning.
					<pitch/> # one or more elements. Equal to the number of pitches in a single at bat.
				</atbat>
			</top>
			<bottom>
				<action/>  # zero or more elements. May precede/succeed an <atbat> element.
				<atbat> # three or more elements. Equal to the number of at bats in the half inning.
					<pitch/> # one or more elements. Equal to the number of pitches in a single at bat.
				</atbat> 
			</bottom>
		</inning>
		<atBat/>
		<deck/>
		<hole/>
	</game>

## <a name="egame">Game Element</a>

The `<game>` element is a container element that does not have any attributes.

## <a name="einning">Inning Element</a>

The `<inning>` element describes a single inning.

	<inning num="1">

### Inning Attributes

+ [Number](#inningnumber)

#### <a name="inningnumber">Number</a>

`num` is the inning number.

## <a name="etop">Top Element</a>

The `<top>` element is a container element that does not have any attributes.

## <a name="ebottom">Bottom Element</a>

The `<bottom>` element is a container element that does not have any attributes.

## <a name="eaction">Action Element</a>

The `<action/>` element describes a particular action in the game.

	<action b="3" s="2" o="1" des="On-field Delay. " des_es="" event="Game Advisory" tfs="180039" tfs_zulu="2011-07-09T18:00:39Z" player="434158" pitch="8"/>

### Action Attributes

+ [Time](#actiontime)
+ [Time Zulu](#actiontimezulu)
+ [Description](#actiondescription)
+ [Spanish Description](#actionspanishdescription)
+ [Event](#actionevent)
+ [Event - 2](#actioneventtwo)
+ [Player](#actionplayer)
+ [Pitch](#actionpitch)
+ [Balls](#actionballs)
+ [Strikes](#actionstrikes)
+ [Outs](#actionouts)
+ [Away Team Runs](#actionawayteamruns)
+ [Home Team Runs](#actionhometeamruns)
+ [Score](#actionscore)

#### <a name="actiontime">Time</a>

`tfs` is the start time of the action in UTC. It has the format `HHMMSS`.

#### <a name="actiontimezulu">Time Zulu</a>

`tfs_zulu` is the start time of the action in UTC. It has the extended format `YYYY-MM-DDTHH:MM:SSZ`.

#### <a name="actiondescription">Description</a>

`des` is a text description of the action.

#### <a name="actionspanishdescription">Spanish Description</a>

`des_es` is a text description of the action in Spanish.

#### <a name="actionevent">Event</a>

`event` is a description of the event. It has one of the following values:

+ `Balk`
+ `Base Running Double Play`
+ `Batter Turn`
+ `Caught Stealing 2B`
+ `Caught Stealing 3B`
+ `Caught Stealing Home`
+ `Defensive Indiff`
+ `Defensive Sub`
+ `Defensive Switch`
+ `Ejection`
+ `Error`
+ `Field Error`
+ `Game Advisory`
+ `N/A`
+ `Offensive sub`
+ `Passed Ball`
+ `Picked off stealing 2B`
+ `Picked off stealing 3B`
+ `Picked off stealing home`
+ `Pickoff 1B`
+ `Pickoff 2B`
+ `Pickoff 3B`
+ `Pickoff Attempt 1B`
+ `Pickoff Attempt 2B`
+ `Pickoff Error 1B`
+ `Pickoff Error 2B`
+ `Pickoff Error 3B`
+ `Pitching Substitution`
+ `Player Injured`
+ `Relief with No Outs`
+ `Runner Advance`
+ `Runner Interference`
+ `Runner Out`
+ `Stolen Base 2B`
+ `Stolen Base 3B`
+ `Stolen Base Home`
+ `Umpire Substitution`
+ `Wild Pitch`

#### <a name="actioneventtwo">Event - 2</a>

`event2` is a description of an event that has occurred after the primary event. If present, it has the following value:

+ `Error`

#### <a name="actionplayer">Player</a>

`player` is the ID number used for the player.

#### <a name="actionpitch">Pitch</a>

`pitch` is the pitch number in the at bat when the action occurred.

#### <a name="actionballs">Balls</a>

`b` is the total number of balls in the count when the action occurred.

#### <a name="actionstrikes">Strikes</a>

`s` is the total number of strikes in the count when the action occurred.

#### <a name="actionouts">Outs</a>

`o` is the total number of outs in the inning when the action occurred.

#### <a name="actionawayteamruns">Away Team Runs</a>

`away_team_runs` is the total number of runs for the away team. Only present when the at bat produces a scoring play.

#### <a name="actionhometeamruns">Home Team Runs</a>

`home_team_runs` is the total number of runs for the home team. Only present when the at bat produces a scoring play.

#### <a name="actionscore">Score</a>

`score` identifies if the at bat produced a scoring play. Only present if a scoring player occurred and has the following value:

+ `T` -- True

## <a name="eatbat">At Bat Element</a>

The `<atbat>` element describes a single at bat.

	<atbat num="20" b="3" s="2" o="1" start_tfs="175721" start_tfs_zulu="2011-07-09T17:57:21Z" batter="116539" pitcher="456034" des="Derek Jeter homers (3) on a fly ball to left field. " des_es="Derek Jeter batea jonrón (3) con elevado por el jardín izquierdo. " event="Home Run" score="T" home_team_runs="1" away_team_runs="1" b1="" b2="" b3="" rbi="1">

### At Bat Attributes

+ [Start Time](#atbatstarttime)
+ [Start Time Zulu](#atbatstarttimezulu)
+ [Batter](#atbatbatter)
+ [Pitcher](#atbatpitcher)
+ [Number](#atbatnumber)
+ [Balls](#atbatballs)
+ [Strikes](#atbatstrikes)
+ [Outs](#atbatouts)
+ [Description](#atbatdescription)
+ [Spanish Description](#)
+ [Event](#atbatevent)
+ [Score](#atbatscore)
+ [Away Team Runs](#atbatawayteamruns)
+ [Home Team Runs](#atbathometeamruns)
+ [Baserunner - 1st Base](#atbatrunnerfirst)
+ [Baserunner - 2nd Base](#atbatrunnersecond)
+ [Baserunner - 3rd Base](#atbatrunnerthird)
+ [RBI](#atbatrbi)

#### <a name="atbatstarttime">Start Time</a>

`start_tfs` is the start time of the at bat in UTC. It has the format `HHMMSS`.

#### <a name="atbatstarttimezulu">Start Time Zulu</a>

`start_tfs_zulu` is the start time of the at bat in UTC. It has the extended format `YYYY-MM-DDTHH:MM:SSZ`.

#### <a name="atbatbatter">Batter</a>

`batter` is the ID number used for the batter.

#### <a name="atbatpitcher">Pitcher</a>

`pitcher` is the ID number used for the pitcher.

#### <a name="atbatnumber">Number</a>

`num` is the overall at bat number for the game.

#### <a name="atbatballs">Balls</a>

`b` is the total number of balls in the count when the at bat completed.

#### <a name="atbatstrikes">Strikes</a>

`s` is the total number of strikes in the count when the at bat completed.

#### <a name="atbatouts">Outs</a>

`o` is the total number of outs in the inning when the at bat completed.

#### <a name="atbatdescription">Description</a>

`des` is a text description of the outcome.

#### <a name="">Spanish Description</a>

`des_es` is a text description of the outcome in Spanish.

#### <a name="atbatevent">Event</a>

`event` identifies the event for the at bat. It has one of the following values:

+ `Batter Interference`
+ `Bunt Groundout`
+ `Bunt Lineout`
+ `Bunt Pop Out`
+ `Catcher Interference`
+ `Double`
+ `Double Play`
+ `Fan interference`
+ `Field Error`
+ `Fielders Choice`
+ `Fielders Choice Out`
+ `Flyout`
+ `Forceout`
+ `Grounded Into DP`
+ `Groundout`
+ `Hit By Pitch`
+ `Home Run`
+ `Intent Walk`
+ `Lineout`
+ `Pop Out`
+ `Runner Out`
+ `Sac Bunt`
+ `Sac Fly`
+ `Sac Fly DP`
+ `Sacrifice Bunt DP`
+ `Single`
+ `Strikeout`
+ `Strikeout - DP`
+ `Triple`
+ `Triple Play`
+ `Walk`
+ `null`

#### <a name="atbatscore">Score</a>

`score` identifies if the at bat produced a scoring play. Only present if a scoring player occurred and has the following value:

+ `T` -- True

#### <a name="atbatawayteamruns">Away Team Runs</a>

`away_team_runs` is the total number of runs for the away team. Only present when the at bat produces a scoring play.

#### <a name="atbathometeamruns">Home Team Runs</a>

`home_team_runs` is the total number of runs for the home team. Only present when the at bat produces a scoring play.

#### <a name="atbatrunnerfirst">Baserunner - 1st Base</a>

`b1` is the ID number used for the player who occupies first base. If there is not a player on first base, the value is an empty string.

#### <a name="atbatrunnersecond">Baserunner - 2nd Base</a>

`b2` is the ID number used for the player who occupies second base. If there is not a player on second base, the value is an empty string.

#### <a name="atbatrunnerthird">Baserunner - 3rd Base</a>

`b3` is the ID number used for the player who occupies third base. If there is not a player on third base, the value is an empty string.

#### <a name="atbatrbi">RBI</a>

`rbi` is the total number of RBI produced by the at bat. It is only present if the at bat produces a scoring play.

## <a name="epitch">Pitch Element</a>

The `<pitch/>` element describes a single pitch from an at bat.
	
	<pitch sv_id="110709_140017" des="In play, run(s)" des_es="En juego, carrera(s)" type="X" start_speed="78.3" pitch_type="CU"/>

### Pitch Attributes

+ [Sportvision ID](#pitchsportvisionid)
+ [Description](#pitchdescription)
+ [Spanish Description](#pitchspanishdescription)
+ [Start Speed](#pitchstartspeed)
+ [End Speed](#pitchendspeed)
+ [Type](#pitchtype)
+ [Pitch Type](#pitchpitchtype)

#### <a name="pitchsportvisionid">Sportvision ID</a>

`sv_id` is the unique Sportvision identifier for the pitch. It takes the format `YYMMDD_HHMMSS` with `HHMMSS` in the Eastern Time.

#### <a name="pitchdescription">Description</a>

`des` is a text description of the pitch outcome. It has one of the following values:

+ `Automatic Ball`
+ `Automatic Strike`
+ `Ball`
+ `Ball In Dirt`
+ `Called Strike`
+ `Foul`
+ `Foul (Runner Going)`
+ `Foul Bunt`
+ `Foul Tip`
+ `Hit By Pitch`
+ `In play, no out`
+ `In play, out(s)`
+ `In play, run(s)`
+ `Intent Ball`
+ `Missed Bunt`
+ `Pitchout`
+ `Swinging Pitchout`
+ `Swinging Strike`
+ `Swinging Strike (Blocked)`

#### <a name="pitchspanishdescription">Spanish Description</a>

`des_es` is the text description of the pitch outcome in Spanish.

#### <a name="pitchstartspeed">Start Speed</a>

`start_speed` is the start speed of the pitch measured in MPH.

#### <a name="pitchendspeed">End Speed</a>

`end_speed` is the end speed of the pitch measured in MPH.

#### <a name="pitchtype">Type</a>

`type` identifies the pitch outcome. It has one of the following values:

+ `B` -- Ball
+ `S` -- Strike
+ `X` -- Ball In Play

#### <a name="pitchpitchtype">Pitch Type</a>

`pitch_type` identifies the type of pitch that was thrown. It has one of the following values:

+ `AB`
+ `CH` -- Changeup
+ `CU` -- Cutter
+ `EP`
+ `FA` -- Fastball
+ `FC` -- Fast Curve
+ `FF` -- Four-seam Fastball
+ `FO`
+ `FS`
+ `FT` -- Two-seam Fastball
+ `IN`
+ `KC` -- Knuckle Curve
+ `KN` -- Knuckleball
+ `PO`
+ `SC` -- Slow Curve
+ `SI` -- Sinker
+ `SL` -- Slider
+ `UN`
+ `""` -- Empty string

## <a name="eatbatfinal">Final At Bat Element</a>

The `<atBat/>` element describes the player at bat when the game ended.

	<atBat pid="448605"/>

### Final At Bat Attributes

+ [ID](#finalatbatid)

#### <a name="finalatbatid">ID</a>

`pid` is the ID number used for the player last at bat when the game ended.

## <a name="edeck">Deck Element</a>

The `<deck/>` element describes the player on deck when the game ended.

	<deck pid="113028"/>

### Deck Attributes

+ [ID](#deckid)

#### <a name="deckid">ID</a>

`pid` is the ID number used for the player on deck when the game ended.

## <a name="ehole">Hole Element</a>

The `<hole/>` element describes the player at bat when the game ended.

	<hole pid="450314"/>

### Hole Attributes

+ [ID](#holeid)

#### <a name="holeid">ID</a>

`pid` is the ID number used for the player in the hole when the game ended.
