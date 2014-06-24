# inning_Scores.xml

The inning_Scores.xml file provides information.... It consists of the following elements:

+ [`<scores>`](#escores)
+ [`<score>`](#escore)
+ [`<action/>`](#eaction)
+ [`<atbat>`](#eatbat)
+ [`<pitch/>`](#epitch)
+ [`<po/>`](#epo)
+ [`<runner/>`](#erunner)

These elements form the following structure:

	<scores>
		<score>
			<action/>
			<atbat>
				<pitch/>
				<po/>
				<runner/>
			</atbat>
		</score>
	</scores>

## <a name="escores">Scores Element</a>

The `<scores>` element describes the home and away team.

	<scores away_team="tba" home_team="nya">
	
### Scores Attributes

+ [Away Team](#scoresawayteam)
+ [Home Team](#scoreshometeam)

#### <a name="scoresawayteam">Away Team</a>

`away_team` is the three-letter team code for the away team. See [here](../team-information.md) for all team information.

#### <a name="scoreshometeam">Home Team</a>

`home_team` is the three-letter team code for the home team. See [here](../team-information.md) for all team information.

## <a name="escore">Score Element</a>

The `<score>` element describes an event that contributed to scoring.

	<score inn="3" atbat_num="20" top_inning="N" home="1" away="1" pbp="Derek Jeter homers (3) on a fly ball to left field. ">

### Score Attributes

+ [Inning](#scoreinning)
+ [Top of Inning](#scoretopofinning)
+ [At Bat Number](#scoreatbat)
+ [Play By Play](#scoreplaybyplay)
+ [Away Team Runs](#scoreaway)
+ [Home Team Runs](#scorehome)

#### <a name="scoreinning">Inning</a>

`inn` is the inning when the scoring occurred.

#### <a name="scoretopofinning">Top of Inning</a>

`top_inning` identifies if the scoring occurred in the top half of the inning. It has one of the following values:

+ `N` -- No
+ `Y` -- Yes

#### <a name="scoreatbat">At Bat</a>

`atbat_num` is the overall at bat number for the game.

#### <a name="scoreplaybyplay">Play By Play</a>

`pbp` is a text description of the play. There appears to be an additional space at the end of the string.

#### <a name="scoreaway">Away Team Runs</a>

`away` is the total number of away team runs *after* the play.

#### <a name="scorehome">Home Team Score</a>

`home` is the total number of home team runs *after* the play.

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
+ `Batter Turn`
+ `Caught Stealing 2B`
+ `Caught Stealing 3B`
+ `Caught Stealing Home`
+ `Defensive Indiff`
+ `Defensive Sub`
+ `Defensive Switch`
+ `Ejection`
+ `Error`
+ `Game Advisory`
+ `N/A`
+ `Offensive sub`
+ `Passed Ball`
+ `Picked off stealing 2B`
+ `Picked off stealing 3B`
+ `Picked off stealing home`
+ `Pickoff 1B`
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

The `<atbat>` element describes the at bat that produced scoring OR was in progress when scoring occurred.

	<atbat num="20" b="3" s="2" o="1" start_tfs="175721" start_tfs_zulu="2011-07-09T17:57:21Z" batter="116539" stand="R" b_height="6-3" pitcher="456034" p_throws="L" des="Derek Jeter homers (3) on a fly ball to left field. " des_es="Derek Jeter batea jonrón (3) con elevado por el jardín izquierdo. " event="Home Run" score="T" home_team_runs="1" away_team_runs="1">

### At Bat Attributes

+ [Start Time](#atbatstarttime)
+ [Start Time Zulu](#atbatstarttimezulu)
+ [At Bat Number](#atbatnumber)
+ [Batter](#atbatbatter)
+ [Stands](#atbatstands)
+ [Height](#atbatheight)
+ [Pitcher](#atbatpitcher)
+ [Pitcher Throws](#atbatpitcherthrows)
+ [Balls](#atbatballs)
+ [Strikes](#atbatstrikes)
+ [Outs](#atbatouts)
+ [Description](#atbatdescription)
+ [Spanish Description](#)
+ [Event](#atbatevent)
+ [Event 2](#atbatevent2)
+ [Event 3](#atbatevent3)
+ [Event 4](#atbatevent4)
+ [Score](#atbatscore)
+ [Away Team Runs](#atbatawayteamruns)
+ [Home Team Runs](#atbathometeamruns)

#### <a name="atbatstarttime">Start Time</a>

`start_tfs` is the start time of the at bat in UTC. It has the format `HHMMSS`.

#### <a name="atbatstarttimezulu">Start Time Zulu</a>

`start_tfs_zulu` is the start time of the at bat in UTC. It has the extended format `YYYY-MM-DDTHH:MM:SSZ`.

#### <a name="atbatnumber">At Bat Number</a>

`num` is the overall at bat number for the game.

#### <a name="atbatbatter">Batter</a>

`batter` is the ID number used for the batter.

#### <a name="atbatstands">Stands</a>

`stand` identifies which side of the plate the player hit from. It has one of the following values:

+ `R` -- Right
+ `L` -- Left

#### <a name="atbatheight">Height</a>

`b_height` is the batter's height. It takes the form `FT-IN`.

#### <a name="atbatpitcher">Pitcher</a>

`pitcher` is the ID number used for the pitcher.

#### <a name="atbatpitcherthrows">Pitcher Throws</a>

`p_throws` identifies which arm the pitcher throws with. It has one of the following values:

+ `R` -- Right
+ `L` -- Left

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

`event` identifies an event for the at bat. It has one of the following values:

+ `Bunt Groundout`
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
+ `Single`
+ `Strikeout`
+ `Strikeout - DP`
+ `Triple`
+ `Walk`

#### <a name="atbatevent2">Event 2</a>

`event2` identifies a second event for the at bat. If present, it has one of the following values:

+ `Caught Stealing 2B`
+ `Error`
+ `Passed Ball`
+ `Pickoff Error 1B`
+ `Pickoff Error 2B`
+ `Runner Out`
+ `Stolen Base 2B`
+ `Stolen Base 3B`
+ `Stolen Base Home`
+ `Wild Pitch`

#### <a name="atbatevent3">Event 3</a>

`event3` identifies a third event for the at bat. If present, it has one of the following values:

+ `Error`
+ `Passed Ball`
+ `Runner Out`
+ `Stolen Base 2B`
+ `Wild Pitch`

#### <a name="atbatevent4">Event 4</a>

`event4` identifies a fourth event for the at bat.If present, it has the following value:

+ `Error`

#### <a name="atbatscore">Score</a>

`score` identifies if the at bat produced a scoring play. Only present if a scoring player occurred and has the following value:

+ `T` -- True

#### <a name="atbatawayteamruns">Away Team Runs</a>

`away_team_runs` is the total number of away team runs *after* the at bat.

#### <a name="atbathometeamruns">Home Team Runs</a>

`home_team_runs` is the total number of home team runs *after* the at bat.

## <a name="epitch">Pitch Element</a>

The `<pitch/>` element describes a single pitch from an at bat.

	<pitch des="In play, run(s)" des_es="En juego, carrera(s)" id="165" type="X" tfs="180015" tfs_zulu="2011-07-09T18:00:15Z" x="102.15" y="154.56" sv_id="110709_140017" start_speed="78.3" end_speed="73.6" sz_top="3.46" sz_bot="1.69" pfx_x="-2.0" pfx_z="-1.27" px="-0.049" pz="2.162" x0="2.155" y0="50.0" z0="6.191" vx0="-4.427" vy0="-114.794" vz0="-1.747" ax="-2.697" ay="18.983" az="-33.818" break_y="23.9" break_angle="5.5" break_length="10.3" pitch_type="CU" type_confidence="2.000" zone="8" nasty="19" spin_dir="301.366" spin_rate="399.184" cc="" mt=""/>
	
### Pitch Attributes

Note: Attribute information taken from [here](https://web.archive.org/web/20090413172551/http://webusers.npl.illinois.edu/~a-nathan/pob/tracking.htm)

+ [Start Time](#pitchstarttime)
+ [Start Time Zulu](#pitchstarttimezulu)
+ [Description](#pitchdescription)
+ [Spanish Description](#pitchspanishdescription)
+ [ID](#pitchid)
+ [Type](#pitchtype)
+ [X Coordinate](#pitchxcoordinate)
+ [Y Coordinate](#pitchycoordinate)
+ [Sportvision ID](#pitchsportvisionid)
+ [Start Speed](#pitchstartspeed)
+ [End Speed](#pitchendspeed)
+ [Top of the Strike Zone](#pitchstrikezonetop)
+ [Bottom of the Strike Zone](#pitchstrikezonebottom)
+ [Pitch Trajectory Deviation - Horizontal](#pitchtrajectorydeviationhorizontal)
+ [Pitch Trajectory Deviation - Vertical](pitchtrajectorydeviationvertical)
+ [Pitch Location - Horizontal](#pitchlocationhorizontal)
+ [Pitch Location - Vertical](#pitchlocationvertical)
+ [Initial Pitch Position - Vertical](#pitchinitialvertical)
+ [Initial Pitch Position - Horiztonal](#pitchinitialhorizontal)
+ [Initial Pitch Tracking Position](#pitchinitialtrackingposition)
+ [Initial Pitch Velocity - Horizontal](#pitchinitialvelocityhorizontal)
+ [Initial Pitch Velocity - Vertical](#pitchinitialvelocityvertical)
+ [Initial Pitch Velocity - Unknown](#pitchinitialvelocityunknown)
+ [Initial Pitch Acceleration - Horizontal](#pitchinitialaccelerationhorizontal)
+ [Initial Pitch Acceleration - Vertical](#pitchinitialaccelerationvertical)
+ [Initial Pitch Acceleration - Unknown](#pitchinitialaccelerationunknown)
+ [Distance of Largest Pitch Trajectory Deviation](#pitchtrajectorylargestdeviationdistance)
+ [Length of Largest Pitch Trajectory Deviation](#pitchtrajectorylargestdeviationlength)
+ [Angle of Pitch Trajectory Deviation](#pitchtrajectorydeviationangle)
+ [Pitch Type](#pitchtype)
+ [Confidence](#pitchconfidence)
+ [Zone](#pitchzone)
+ [Nasty](#pitchnasty)
+ [Pitch Spin Direction](#pitchspindirection)
+ [Pitch Spin Rate](#pitchspinrate)
+ [Closed Caption](#pitchclosedcaption)
+ [Media Thumbnail](#pitchmediathumbnail)
+ [Runner on First Base](#pitchrunneronfirst)
+ [Runner on Second Base](#pitchrunneronsecond)
+ [Runner on Third Base](#pitchrunneronthird)

#### <a name="pitchstarttime">Start Time</a>

`start_tfs` is the start time of the at bat in UTC. It has the format `HHMMSS`.

#### <a name="pitchstarttimezulu">Start Time Zulu</a>

`start_tfs_zulu` is the start time of the at bat in UTC. It has the extended format `YYYY-MM-DDTHH:MM:SSZ`.

#### <a name="pitchdescription">Description</a>

`des` is the text description of the outcome. It has one of the following values:

+ `Automatic Ball`
+ `Ball`
+ `Ball In Dirt`
+ `Called Strike`
+ `Foul`
+ `Foul (Runner Going)`
+ `Foul Bunt`
+ `Foul Pitchout`
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

`des_es` is the text description of the outcome in Spanish.

#### <a name="pitchid">ID</a>

`id` is a unique identifier for the pitch. The number is **NOT** the overall pitch number for the game.

#### <a name="pitchtype">Type</a>

`type` identifies the type outcome of the pitch. It has one of the following values:

+ `B` -- Ball
+ `S` -- Strike
+ `X` -- Ball In Play

#### <a name="pitchxcoordinate">X Coordinate</a>

`x` is the x coordinate where the pitch crossed the plate. See the explanation [here]().

#### <a name="pitchycoordinate">Y Coordinate</a>

`y` is the y coordinate where the pitch crossed the plate. See the explanation [here]().

#### <a name="pitchsportvisionid">Sportvision ID</a>

`sv_id` is the unique Sportvision identifier for the pitch. It takes the format `YYMMDD_HHMMSS` with `HHMMSS` in the Eastern Time.

#### <a name="pitchstartspeed">Start Speed</a>

`start_speed` is the start speed of the pitch measured in MPH.

#### <a name="pitchendspeed">End Speed</a>

`end_speed` is the end speed of the pitch measured in MPH.

#### <a name="pitchstrikezonetop">Top of the Strike Zone</a>

`sz_top` is the top of the strike zone measured in feet. It is adjusted for the player at bat.

#### <a name="pitchstrikezonebottom">Bottom of the Strike Zone</a>

`sz_bot` is the bottom of the strike zone measured in feet. It is adjusted for the player at bat.

#### <a name="pitchtrajectorydeviationhorizontal">Pitch Trajectory Deviation - Horizontal</a>

`pfx_x` is the deviation measured in inches of the pitch trajectory from a straight line in the horizontal direction between 40 feet and the front of home plate (1.417 feet).

#### <a name="pitchtrajectorydeviationvertical">Pitch Trajectory Deviation - Vertical</a>

`pfx_z` is the deviation measured in inches of the pitch trajectory from a straight line in the vertical direction between 40 feet and the front of home plate (1.417 feet).

#### <a name="pitchlocationhorizontal">Pitch Location - Horizontal</a>

`px` is the location of the pitch horizontally as it crosses home plate measured in feet.

#### <a name="pitchlocationvertical">Pitch Location - Vertical</a>

`pz` is the location of the pitch vertically as it crosses home plate measured in feet.

#### <a name="pitchinitialhorizontal">Initial Pitch Position - Horiztonal</a>

`x0` is the initial horizontal position measured in feet.

#### <a name="pitchinitialvertical">Initial Pitch Position - Vertical</a>

`z0` is the initial vertical position measured in feet.

#### <a name="pitchinitialtrackingposition">Initial Pitch Tracking Position</a>

`y0` is the initial tracking position and is measured at 50 feet from home plate.

#### <a name="pitchinitialvelocityhorizontal">Initial Pitch Velocity - Horizontal</a>

`vx0` is the initial velocity in the horizontal direction measured in ft/s.

#### <a name="pitchinitialvelocityvertical">Initial Pitch Velocity - Vertical</a>

`vz0` is the initial velocity in the vertical direction measured in ft/s.

#### <a name="pitchinitialvelocityunknown">Initial Pitch Velocity - Unknown</a>

`vy0` is an unknown measure of velocity in ft/s.

#### <a name="pitchinitialaccelerationhorizontal">Initial Pitch Acceleration - Horizontal</a>

`ax` is the initial acceleration in the horizontal direction measured in ft/s<sup>2</sup>.

#### <a name="pitchinitialaccelerationvertical">Initial Pitch Acceleration - Vertical</a>

`az` is the initial acceleration in the vertical direction measured in ft/s<sup>2</sup>.

#### <a name="pitchinitialaccelerationunknown">Initial Pitch Acceleration - Unknown</a>

`ay` is the initial acceleration in the unknown direction measured in ft/s<sup>2</sup>.

#### <a name="pitchtrajectorylargestdeviationdistance">Distance of Largest Pitch Trajectory Deviation</a>

`break_length` is the largest deviation in inches, of the actual from the straight-line trajectory.

#### <a name="pitchtrajectorylargestdeviationlength">Length of Largest Pitch Trajectory Deviation</a>

`break_y` is the y-distance from home plate where the maximum deviation occurs.

#### <a name="pitchtrajectorydeviationangle">Angle of Pitch Trajectory Deviation</a>

`break_angle` is the direction of the deviation. Pitches that break away from a right handed batter have a negative angle. Pitches that break in to a right handed batter have a positive angle.

#### <a name="pitchpitchtype">Pitch Type</a>

`pitch_type` identifies the type of pitch that was thrown. It has one of the following values:

+ `AB` -- 
+ `CH` -- Changeup
+ `CU` -- Cutter
+ `EP` -- Eephus
+ `FA` -- Fastball
+ `FC` -- Fastball (Cutter)
+ `FF` -- Four-seam Fastball
+ `FO` --
+ `FS` -- Splitter
+ `FT` -- Two-seam Fastball
+ `IN` --
+ `KC` -- Knuckle Curve
+ `KN` -- Knuckleball
+ `PO` -- Pitch out
+ `SC` --
+ `SI` -- Sinker
+ `SL` -- Slider
+ `UN` -- Unidentified

#### <a name="pitchconfidence">Confidence</a>

`type_confidence` is a measure of the confidence that the pitch thrown matches the `pitch_type` value.

#### <a name="pitchzone">Zone</a>

`zone` is the zone where the pitch was thrown. See [here]() for further explanation.

#### <a name="pitchnasty">Nasty</a>

`nasty` is a measure of how hard the pitch is to hit on a scale of 0-100.

#### <a name="pitchspindirection">Pitch Spin Direction</a>

`spin_dir` is the measure of the pitch's spin direction.

#### <a name="pitchspinrate">Pitch Spin Rate</a>

`spin_rate` is the measure of the pitch's spin rate.

#### <a name="pitchclosedcaption">Closed Caption</a>

`cc` is the closed caption text for the pitch.

#### <a name="pitchmediathumbnail">Media Thumbnail</a>

`mt` is the media thumbnail for the pitch. If present, it's value is a relative path to `mlb.mlb.com`. May be an empty string

#### <a name="pitchrunneronfirst">Runner on First Base</a>

`on_1b` is the ID number used for the runner on First Base. Only present if a runner occupies the base at the start of the pitch.

#### <a name="pitchrunneronsecond">Runner on Second Base</a>

`on_2b` is the ID number used for the runner on Second Base. Only present if a runner occupies the base at the start of the pitch.

#### <a name="pitchrunneronthird">Runner on Third Base</a>

`on_3b` is the ID number used for the runner on Third Base. Only present if a runner occupies the base at the start of the pitch.

## <a name="epo">PO Element</a>

The `<po/>` element describes a single pickoff attempt.

	<po des="Pickoff Attempt 1B"/>
	
### Pickoff Attributes

+ [Description](#pickoffdescription)

#### <a name="pickoffdescription">Description</a>

`des` is a text description of the attempt. It has one of the following values:

+ `Pickoff 1B`
+ `Pickoff 3B`
+ `Pickoff Attempt 1B`
+ `Pickoff Attempt 2B`
+ `Pickoff Attempt 3B`
+ `Pickoff Error 1B`
+ `Pickoff Error 2B`
+ `Pickoff Error 3B`

## <a name="erunner">Runner Element</a>

The `<runner/>` element describes a single baserunner during the at bat. If the at bat results in a home run, there is a single baserunner element.

	<runner id="455755" start="3B" end="" event="Single" score="T" rbi="T" earned="T"/>
	
**Note**: If the `start` and `end` element is an empty string, the batter hit a homerun.

### Runner Attributes

+ [ID](#runnerid)
+ [Start](#runnerstart)
+ [End](#runnerend)
+ [Event](#runnerevent)
+ [Earned](#runnerearned)
+ [Score](#runnerscore)
+ [RBI](#runnerbi)

#### <a name="runnerid">ID</a>

`id` is the ID number used for the baserunner.

#### <a name="runnerstart">Start</a>

`start` identifies the initial base for the runner at the start of the at bat. It has one of the following values:

+ `1B` -- First Base
+ `2B` -- Second Base
+ `3B` -- Third Base
+ `""` -- Empty string

#### <a name="runnerend">End</a>

`end` identifies the final base for the runner at the end of the at bat. It has one of the following values:

+ `1B` -- First Base
+ `2B` -- Second Base
+ `3B` -- Third Base
+ `""` -- Empty string

#### <a name="runnerevent">Event</a>

`event` identifies the event for a baserunner. It has one of the following values:

+ `Balk`
+ `Bunt Groundout`
+ `Catcher Interference`
+ `Caught Stealing 2B`
+ `Caught Stealing 3B`
+ `Caught Stealing Home`
+ `Defensive Indiff`
+ `Double`
+ `Double Play`
+ `Error`
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
+ `Passed Ball`
+ `Picked off stealing 2B`
+ `Picked off stealing 3B`
+ `Picked off stealing home`
+ `Pickoff 1B`
+ `Pickoff 3B`
+ `Pickoff Attempt 1B`
+ `Pickoff Attempt 2B`
+ `Pickoff Attempt 3B`
+ `Pickoff Error 1B`
+ `Pickoff Error 2B`
+ `Pickoff Error 3B`
+ `Pop Out`
+ `Runner Interference`
+ `Runner Out`
+ `Sac Bunt`
+ `Sac Fly`
+ `Sac Fly DP`
+ `Single`
+ `Stolen Base 2B`
+ `Stolen Base 3B`
+ `Stolen Base Home`
+ `Strikeout`
+ `Strikeout - DP`
+ `Triple`
+ `Walk`
+ `Wild Pitch`

#### <a name="runnerearned">Earned</a>

`earned` identifies if the baserunner's run was earned. If present, it has the following values:

+ `T` -- True

#### <a name="runnerscore">Score</a>

`score` identifies if the baserunner scored a run. If present it has the following value:

+ `T` -- True

#### <a name="runnerbi">RBI</a>

`rbi` identifies if the baserunner's run was an RBI for the batter. If present, it has one of the following values:

+ `T` -- True
