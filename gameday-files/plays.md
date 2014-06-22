# plays.xml

The plays.xml file provides information about the final play that produced a winning run in the bottom of the last inning or the final at bat. It consists of the following elements:

+ [`<game>`](#egame)
+ [`<score/>`](#escore)
+ [`<review/>`](#ereview)
+ [`<players>`](#eplayers)
+ [`<batter>`](#ebatter)
+ [`<ab/>`](#eab)
+ [`<pitcher/>`](#epitcher)
+ [`<deck/>`](#edeck)
+ [`<hole/>`](#ehole)
+ [`<splits/>`](#esplits)
+ [`<action/>`](#eaction)
+ [`<atbat>`](#eatbat)
+ [`<p/>`](#ep)
+ [`<po/>`](#epo)
+ [`<runner/>`](#erunner)
+ [`<field>`](#efield)
+ [`<offense>`](#eoffense)
+ [`<man>`](#eman)
+ [`<defense>`](#edefense)
+ [`<ball>`](#eball)
+ [`<lineup>`](#elineup)
+ [`<team>`](#eteam)
+ [`<control>`](#econtrol)
+ [`<weather>`](#eweather)

These elements form the following structure:
	
	<game>
		<score/>
		<review/> # only present if game is from 2011/2012 playoffs OR 2013-present
		<players>
			<batter>
				<ab/> # one ore more elements, matches number of at bats for the player in reverse chronological order. 
			</batter>
			<pitcher/>
			<deck/>
			<hole/>
		</players>
		<splits/>
		<action/> # zero or one element. Present if game is won in the bottom of the last winning. Not present if <atbat> element exists.
		<atbat> # zero or one element. Present if last at bat results in an out. Not present if <action/> element exists. 
			<p/> # Multiple elements, equal to the total number of pitches in the final at bat
			<po/> # May precede/succeed a <p/> element
			<runner/> # zero or more elements.
		</atbat>
		<field>
			<offense>
				<man/> # zero or more elements. Equal to the number of men who reached base safely in the final inning.
			</offense>
			<defense>
				<man/> # 9 elements. Equal to the number of players in the field in the final inning.
			</defense>
			<ball/>
		</field>
			<lineup>
				<team>
					<man/> # multiple elements
				</team>
				<team>
					<man/> # multiple elements
				</team>
			</lineup>
			<control/>
			<weather/>
		</game>
		
## <a name="egame">Game Element</a>

The `<game>` element describes basic game information.

	<game id="2011_07_09_tbamlb_nyamlb_1" status_ind="F" status="Final" inning="9" top_inning="T" b="0" s="0" o="3" inning_state="" event="at_bat_start">
	
### Game Attributes

+ [ID](#gid)
+ [Balls](#gballs)
+ [Strikes](#gstrikes)
+ [Outs](#gouts)
+ [Inning](#ginning)
+ [Inning State](#ginningstate)
+ [Top of Inning](#gtopofinning)
+ [Status](#gstatus)
+ [Status Indicator](#gstatusindicator)
+ [Reason](#greason)
+ [Event](#gevent)

#### <a name="gid">ID</a>

`id` is a unique identifier for the game.

#### <a name="gballs">Balls</a>

`b` is the total number of balls when the final out was recorded. It has one of the following values:

+ `0`
+ `1`
+ `3`

#### <a name="gstrikes">Strikes</a>

`s` is the total number of strikes when the final out was recorded. It has one of the following values:

+ `0`
+ `1`
+ `2`
+ `3`

#### <a name="gouts">Outs</a>

`o` is the total number of outs when the final out was recorded. It has one of the following values:

+ `0`
+ `1`
+ `2`
+ `3`

#### <a name="ginning">Inning</a>

`inning` is the total number of innings played.

#### <a name="ginningstate">Inning State</a>

`inning_state` is a text description of the inning when the game concluded. It appears that this value is an empty string.

#### <a name="gtopofinning">Top of Inning</a>

`top_inning` identifies if the game concluded in the top of the last scheduled inning. It has one of the following values:

+ `F` -- False
+ `T` -- True

#### <a name="gstatus">Status</a>

`status` identifies the game status. It has one of the following values:

+ `Completed Early`
+ `Final`
+ `Game Over`
+ `Postponed`

#### <a name="gstatusindicator">Status Indicator</a>

`status_ind` identifies the game status as an abbreviation. It has one of the following values:

+ `F` -- Final
+ `FT` -- Final and score tied
+ `FR` -- Final and called due to rain
+ `DR` -- Delayed due to rain
+ `DO` -- (Delayed Other?)
+ `FO` -- Final (completed early, reason: Other)
+ `O` -- (Other?)

#### <a name="greason">Reason</a>

`reason` is the reason for game stoppage. If present, it has one of the following values:

+ `Tied`
+ `Rain`
+ `Snow`
+ `Other`

#### <a name="gevent">Event</a>

`event` is the event that led to the final play. It has one of the following values:

+ `at_bat_start`
+ `single`
+ `double`
+ `triple`
+ `home_run`
+ `walk`
+ `hit_by_pitch`
+ `sac_bunt`
+ `sac_fly`
+ `strikeout`
+ `balk`
+ `wild_pitch`
+ `passed_ball`
+ `error`
+ `double_play`
+ `pickoff_1b`
+ `pickoff_2b`
+ `pickoff_caught_stealing_2b`
+ `caught_stealing_2b`
+ `caught_stealing_3b`
+ `stolen_base_2b`
+ `stolen_base_3b`
+ `pinch hitter`
+ `pinch runner`
+ `pitching_substitution`
+ `relief_no_out`

## <a name="escore">Score Element</a>

The `<score/>` element describes basic line score information.

	<score ar="4" ah="5" ae="0" hr="5" hh="10" he="0"/>

### Score Attributes

+ [Away Team Runs](#scoreawayruns)
+ [Away Team Hits](#scoreawayhits)
+ [Away Team Errors](#scoreawayerrors)
+ [Home Team Runs](#scorehomeruns)
+ [Home Team Hits](#scorehomehits)
+ [Home Team Errors](#scorehomeerrors)

#### <a name="scoreawayruns">Away Team Runs</a>

`ar` is the total number of runs for the away team.

#### <a name="scoreawayhits">Away Team Hits</a>

`ah` is the total number of hits for the away team.

#### <a name="scoreawayerrors">Away Team Errors</a>

`ae` is the total number of errors for the away team.

#### <a name="scorehomeruns">Home Team Runs</a>

`hr` is the total number of runs for the home team.

#### <a name="scorehomehits">Home Team Hits</a>

`hh` is the total number of hits for the home team.

#### <a name="scorehomeerrors">Home Team Errors</a>

`he` is the total number of errors for the home team.

## <a name="ereview">Review Element</a>

The `<review/>` element describes the challenges for each team. This element is present if the game is from the 2011/2012 playoffs OR the 2013 regular season to present.

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

## <a name="eplayers">Players Element</a>

The `<players>` element is a container element that does not have any attributes.

## <a name="ebatter">Batter Element</a>

The `<batter/>` element describes the last batter in the game.

	<batter pid="448605" team_abbrev="TB" team_id="139" parent_team_abbrev="" parent_team_id="" current_position="LF" stand="R" b_height="6-1" ab="2" h="0" avg=".276" boxname="Ruggiano">

### Batter Attributes

+ [ID](#batterid)
+ [Boxname](#batterboxname)
+ [Height](#batterheight)
+ [Stands](#batterstands)
+ [Current Position](#battercurrentposition)
+ [At Bat](#batteratbat)
+ [Hits](#batterhits)
+ [Batting Average](#batterbattingaverage)
+ [Team ID](#batterteamid)
+ [Team Abbreviation](#batterteamabbrevation)
+ [Parent Team ID](#batterparentteamid)
+ [Parent Team Abbreviation](#batterparentteamabbreviation)

#### <a name="batterid">ID</a>

`pid` is the ID number used for the player.

#### <a name="batterboxname">Boxname</a>

`boxname` is the player's name as it appears in the box score.

#### <a name="batterheight">Height</a>

`b_height` is the player's height.

#### <a name="batterstands">Stands</a>

`stand` identifies which side of the plate the player hits from. It has one of the following values:

+ `R` -- Right
+ `L` -- Left
+ `S` -- Switch

#### <a name="battercurrentposition">Current Position</a>

`current_position` is the player's current position. It has one of the following values:

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

#### <a name="batteratbat">At Bat</a>

`ab` is the total number of at bats for the player in the game.

#### <a name="batterhits">Hits</a>

`h` is the total number of hits for the player in the game.

#### <a name="batterbattingaverage">Batting Average</a>

`avg` is the player's batting average, season to date.

#### <a name="batterteamid">Team ID</a>

`team_id` is the ID number used for the player's team. See all team ID numbers [here](./team-information).

#### <a name="batterteamabbrevation">Team Abbreviation</a>

`team_abbrev` is the abbreviation used for the player's team. See all team abbreviations [here](./team-information).

#### <a name="batterparentteamid">Parent Team ID</a>

`parent_team_id` is the ID number used for the parent team. If the player's team is a Major League team, this value will be an empty string OR the ID number used for the team.

#### <a name="batterparentteamabbreviation">Parent Team Abbreviation</a>

`parent_team_abbrev` is the abbreviation used for the parent team. If the player's team is a Major League team, this value will be an empty string OR the abbreviation used for the team.

## <a name="eab">AB Element</a>

The `<ab/>` element describes a single at bat.

	<ab inning="9" event="Groundout"/>

### AB Attributes

+ [Inning](#abinning)
+ [Event](#abevent)

#### <a name="abinning">Inning</a>

`inning` is the inning number when the at bat occurred.

#### <a name="abevent">Event</a>

`event` is the outcome of the at bat. It has one of the following values:

+ `Single`
+ `Double`
+ `Triple`
+ `Home Run`
+ `Walk`
+ `Intent Walk`
+ `Hit By Pitch`
+ `Sac Bunt`
+ `Sac Fly`
+ `Strikeout`
+ `Strikeout - DP`
+ `Bunt Groundout`
+ `Bunt Lineout`
+ `Bunt Pop Out`
+ `Field Error`
+ `Fielders Choice`
+ `Fielders Choice Out`
+ `Forceout`
+ `Groundout`
+ `Lineout`
+ `Pop Out`
+ `Flyout`
+ `Grounded Into DP`
+ `Double Play`
+ `Triple Play`
+ `Batter Interference`
+ `Catcher Interference`
+ `Fan interference`

## <a name="epitcher">Pitcher Element</a>

The `<pitcher/>` element describes the last pitcher in the game.

	<pitcher pid="121250" p_throws="R" pitches="11" strikes="7" balls="4" era="1.85" boxname="Rivera"/>

### Pitcher Attributes

+ [ID](#pitcherid)
+ [Boxname](#pitcherboxname)
+ [Throws](#pitcherthrows)
+ [Balls](#pitcherballs)
+ [Strikes](#pitcherstrikes)
+ [Pitches](#pitcherpitches)
+ [ERA](#pitcherera)

#### <a name="pitcherid">ID</a>

`pid` is the ID number used for the player.

#### <a name="pitcherboxname">Boxname</a>

`boxname` is the player's name as it appears in the box score.

#### <a name="pitcherthrows">Throws</a>

`p_throws` identifies which arm the pitcher throws with. It has one of the following values:

+ `R` -- Right
+ `L` -- Left

#### <a name="pitcherballs">Balls</a>

`balls` is the total number of balls thrown by the pitcher.

#### <a name="pitcherstrikes">Strikes</a>

`strikes` is the total number of strikes thrown by the pitcher.

#### <a name="pitcherpitches">Pitches</a>

`pitches` is the total number of pitches thrown by the pitcher

#### <a name="pitcherera">ERA</a>

`era` is the pitcher's ERA, season to date.

## <a name="edeck">Deck Element</a>

The `<deck/>` element describes the player on deck when the game ended.

	<deck pid="113028" boxname="Damon"/>

### Deck Attribtues

+ [ID](#deckid)
+ [Boxname](#deckboxname)

#### <a name="deckid">ID</a>

`pid` is the ID number used for the player.

#### <a name="deckboxname">Boxname</a>

`boxname` is the player's name as it appears in the box score.

## <a name="ehole">Hole Element</a>

The `<hole/>` element describes the player in the hole when the game ended.

	<hole pid="450314" boxname="Zobrist"/>

### Hole Attributes

+ [ID](#holeid)
+ [Boxname](#holeboxname)

#### <a name="holeid">ID</a>

`pid` is the ID number used for the player.

#### <a name="holeboxname">Boxname</a>

`boxname` is the player's name as it appears in the box score.

## <a name="esplits">Splits Element</a>

The `<splits/>` element describes the split screen of the Gameday application.

	<splits batter="vs_RHP" pitcher="vs_LHB" runner="Empty"/>
	
### Splits Attributes

+ [Batter](#splitsbatter)
+ [Pitcher](#splitspitcher)
+ [Runner](#splitsrunner)

#### <a name="splitsbatter">Batter</a>

`batter` identifies the split screen information for the batter. It has one of the following values:

+ `vs_RHP` -- Stats versus right handed pitchers
+ `vs_LHP` -- Stats versus left handed pitchers

#### <a name="splitspitcher">Pitcher</a>

`pitcher` identifies the split screen information for the batter. It has one of the following values:

+ `vs_RHB` -- Stats versus right handed batters
+ `vs_LHB` -- Stats versus left handed batters

#### <a name="splitsrunner">Runner</a>

`runner` describes the baserunner(s) for the final at bat. It has one of the following values:

+ `Empty`
+ `Men_On`
+ `Loaded`
+ `RISP`

## <a name="eaction">Action Element</a>

The `<action/>` element describes the final play that scored the winning run in the bottom of the last inning.

	<action des="Russell Martin singles on a fly ball to left fielder Matt Tuiasosopo. Neil Walker scores. Andrew McCutchen to 3rd. Gaby Sanchez to 2nd. " des_es="Russell Martin pega sencillo con elevado a jardinero izquierdo Matt Tuiasosopo. Neil Walker anota Andrew McCutchen a 3ra. Gaby Sanchez a 2da. " event="Relief with No Outs" player="446367"/>

### Action Attributes

+ [Description](#actiondescription)
+ [Spanish Description](#actionspanishdescription)
+ [Player](#actionplayer)
+ [Event](#actionevent)

#### <a name="actiondescription">Description</a>

`des` is the text description of the final play.

#### <a name="actionspanishdescription">Spanish Description</a>

`des_es` is the text description of the final play in Spanish.

#### <a name="actionplayer">Player</a>

`player` is the ID number used for the player.

#### <a name="actionevent">Event</a>

`event` identifies the event for the action. It has one of the following values:

+ `Game Advisory`
+ `Defensive Switch`
+ `Pitching Substitution`
+ `Relief with No Outs`

## <a name="eatbat">At Bat Element</a>

The `<atbat>` element describes the final at bat in detail. 

### At Bat Attributes

+ [Description](#atbatdescription)
+ [Spanish Description](#atbatspanishdescription)
+ [Player](#atbatplayer)
+ [Number](#atbatnumber)
+ [Event](#atbatevent)

#### <a name="atbatdescription">Description</a>

`des` is the text description of the outcome.

#### <a name="atbatspanishdescription">Spanish Description</a>

`des_es` is the text description of the outcome in Spanish.

#### <a name="atbatplayer">Player</a>

`player` is the ID number used for the player.

#### <a name="atbatnumber">Number</a>

`num` is the overall at bat number for the game.

#### <a name="atbatevent">Event</a>

`event` is the the outcome of the final at bat. It has one of the following values:

+ `Single`
+ `Home Run`
+ `Walk`
+ `Wild Pitch`
+ `Sac Fly`
+ `Strikeout`
+ `Strikeout - DP`
+ `Forceout`
+ `Runner Out`
+ `Error`
+ `Grounded Into DP`
+ `Double Play`
+ `Pickoff 1B`
+ `Pickoff 2B`
+ `Picked off stealing 2B`
+ `Caught Stealing 2B`
+ `Left On Base`
+ `Pinch Runner`
+ `Pitching Substitution`
+ `Defensive Sub`
+ `Ejection`
+ `Game Advisory`
+ `null`

## <a name="ep">P Element</a>

The `<p/>` element describes a single pitch in the final at bat.

	<p type="S" id="631" x="100.43" y="136.43" des="Foul" des_es="Foul" sv_id="110709_161641" start_speed="93.1" end_speed="86.7" sz_top="3.26" sz_bot="1.57" pfx_x="1.21" pfx_z="9.08" px="0.021" pz="3.036" x0="-2.041" y0="50.0" z0="6.083" vx0="5.156" vy0="-136.323" vz0="-5.514" ax="2.297" ay="26.281" az="-14.791" break_y="23.9" break_angle="-11.6" break_length="3.4" pitch_type="FC" type_confidence="2.000" zone="2" nasty="45" spin_dir="172.474" spin_rate="1866.022" cc=""/>

### P Attributes

Note: Attribute information taken from [here](https://web.archive.org/web/20090413172551/http://webusers.npl.illinois.edu/~a-nathan/pob/tracking.htm)

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

#### <a name="pitchdescription">Description</a>

`des` is the text description of the outcome. It has one of the following values:

+ `Ball`
+ `Ball In Dirt`
+ `Automatic Ball`
+ `Called Strike`
+ `Swinging Strike`
+ `Swinging Strike (Blocked)`
+ `Foul`
+ `Foul (Runner Going)`
+ `Foul Bunt`
+ `Foul Tip`
+ `Hit By Pitch`
+ `In play, no out`
+ `In play, out(s)`
+ `In play, run(s)`
+ `Missed Bunt`
+ `Pitchout`

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

+ `CH` -- Changeup
+ `CU -- Cutter
+ `EP` 
+ `FA` -- Fastball
+ `FC` -- Fast Curve
+ `FF` -- Four Seam Fastball
+ `FO` -- Forkball
+ `FS` -- 
+ `FT` -- Two Seam Fastball
+ `KC` -- Knuckle Curve
+ `KN` -- Knuckleball
+ `PO` -- 
+ `SC` -- Slider Curve
+ `SI` -- Sinker
+ `SL` -- Slider

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

## <a name="epo">PO Element</a>

The `<po/>` element describes a single pickoff attempt. It may precede or succeed a `<p/>` element. There also may be multiple `<po/>` elements in succession.

	<po des="Pickoff Attempt 1B"/>

### PO Attributes

+ [Description](#podescription)

#### <a name="podescription>Description</a>

`des` is the text description of the pickoff attempt. It has one of the following values:

+ `Pickoff 1B`
+ `Pickoff 2B`
+ `Pickoff Attempt 1B`
+ `Pickoff Attempt 2B`
+ `Pickoff Attempt 3B`
+ `Pickoff Error 1B`

## <a name="erunner">Runner Element</a>

The `<runner/>` element describes a single baserunner during the final at bat.

### Runner Attributes

+ [ID](#runnerid)
+ [Start](#runnerstart)
+ [End](#runnerend)
+ [Event](#runnerevent)
+ [Score](#runnerscore)

#### <a name="runnerid">ID</a>

`id` is the ID number used for the player occupying the base.

#### <a name="runnerstart">Start</a>

`start` identifies the starting base for the runner. It has one of the following values:

+ `1B`
+ `2B`
+ `3B`
+ `""` -- Empty string (runner didn't advance)

#### <a name="runnerend">End</a>

`end` identifies the ending base for the runner. It has one of the following values:

+ `1B`
+ `2B`
+ `3B`
+ `""` -- Empty string (runner didn't advance)

#### <a name="runnerevent">Event</a>

`event` is the outcome of the at bat while the runner is on base. It has one of the following values:

+ `Home Run`
+ `Wild Pitch`
+ `Strikeout`
+ `Strikeout - DP`
+ `Grounded Into DP`
+ `Double Play`
+ `Left On Base`
+ `Pickoff 1B`
+ `Pickoff 2B`

#### <a name="runnerscore">Score</a>

`score` identifies if the runner scored. If present, it has the following value:

+ `T` -- True

## <a name="efield">Field Element</a>

The `<field>` element is a container element that does not have any attributes.

## <a name="eoffense">Offense Element</a>

The `<offense>` element describes team information for the team last at bat.

	<offense type="away" id="tba">

### Offense Attributes

+ [ID](#offenseid)
+ [Type](#offensetype)

#### <a name="offenseid">ID</a>

`id` is the three-letter identifier used for the team. See all team codes [here](./team-information).

#### <a name="offensetype">Type</a>

`type` identifies if the team at bat is home or away. It has one of the following values:

+ `away`
+ `home`

## <a name="eman">Man Element</a>

The `<man/>` element describes a single player. It is seen in three different places with three different sets of attributes. All three are described below.

1) As a child of the `<offense>` element.

	<man bnum="1" pid="488671" boxname="Avila" note="Walk" sb="0" cs="0"/>
	
Here the `<man/>` element describes a single player who reached base in the final inning OR their game at bat record if the game ended before the at bat completed.

### Man Attributes - Offense

+ [ID](#offensemanid)
+ [Boxname](#offensemanboxname)
+ [Batter Number](#offensemanbatternumber)
+ [Home Runs](#offensemanhomeruns)
+ [RBI](#offensemanrbi)
+ [Stolen Bases](#offensemanstolenbases)
+ [Caught Stealing](#offensemancaughtstealing)
+ [Note](#offensemannote)

#### <a name="offensemanid">ID</a>

`pid` is the ID number used for the player.

#### <a name="offensemanboxname">Boxname</a>

`boxname` is the player's name as it appears in the box score.

#### <a name="offensemanbatternumber">Batter Number</a>

`bnum` is the at bat number for the inning.

#### <a name="offensemanhomeruns">Home Runs</a>

`hrs` is the total number of home runs for the player, season to date.

#### <a name="offensemanrbi">RBI</a>

`rbis` is the total number of RBI for the player, season to date.

#### <a name="offensemanstolenbases">Stolen Bases</a>

`sb` is the total number of stolen bases for the player, season to date.

#### <a name="offensemancaughtstealing">Caught Stealing</a>

`cs` is the total number of times caught stealing for the player, season to date.

#### <a name="offensemannote">Note</a>

`note` identifies how the player reached base OR their at bat record for the game if the game ended without completing the at bat. It has one of the following values:

+ `Single`
+ `Double`
+ `Triple`
+ `Walk`
+ `Intent Walk`
+ `Hit By Pitch`
+ `Strikeout`
+ `Sac Bunt`
+ `Sac Fly`
+ `Field Error`
+ `Fielders Choice`
+ `Fielders Choice Out`
+ `Forceout`
+ `Grounded Into DP`
+ `Double Play`
+ `Pinch Runner`
+ `Catcher Interference`
+ `Fan interference`

The following are *common* values if the at bat did not complete:

+ `0-for-0`
+ `0-for-1`
+ `0-for-2`
+ `0-for-3`
+ `0-for-4`
+ `1-for-1`
+ `1-for-2`
+ `1-for-3`
+ `1-for-4`
+ `1-for-5`
+ `2-for-3`
+ `2-for-4`
+ `3-for-4`

2) 1. As a child of the `<defense>` element.

	<man pid="431145" s_po="454" s_ass="48" s_err="6" s_fldg=".988" c_sb="50" c_cs="18" pos="c"/>
	
Here the `<man/>` element describes a single player in the field during the final inning.

### Man Attributes - Defense

+ [ID](#defensemanid)
+ [Position](#defensemanposition)
+ [Assists](#defensemanassists)
+ [Errors](#defensemanerrors)
+ [Putouts](#defensemanputouts)
+ [Fielding Percentage](#defensemanfieldingpercentage)
+ [Stolen Bases - Pitcher](#defensemanpitcherstolenbases)
+ [Caught Stealing - Pitcher](#defensemanpitchercaughtstealing)
+ [Stolen Bases - Catcher](#defensemancatcherstolenbases)
+ [Caught Stealing - Catcher](#defensemancatchercaughtstealing)

#### <a name="defensemanid">ID</a>

`pid` is the ID number used for the player.

#### <a name="defensemanposition">Position</a>

`pos` is the player's position. It has one of the following values:

+ `p`
+ `c`
+ `1b`
+ `2b`
+ `3b`
+ `ss`
+ `lf`
+ `cf`
+ `rf`

#### <a name="defensemanassists">Assists</a>

`s_ass` is the total number of assists by the player, season to date.

#### <a name="defensemanerrors">Errors</a>

`s_err` is the total number of errors by the player, season to date.

#### <a name="defensemanputouts">Putouts</a>

`s_po` is the total number of putouts by the player, season to date.

#### <a name="defensemanfieldingpercentage">Fielding Percentage</a>

`s_fldg` is the fielding percentage of the player, season to date.

#### <a name="defensemanpitcherstolenbases">Stolen Bases - Pitcher</a>

`p_sb` is the total number of players who have stolen a base on the pitcher, season to date. Only present if the player is the current pitcher.

#### <a name="defensemanpitchercaughtstealing">Caught Stealing - Pitcher</a>

`p_cs` is the total number of players who have been caught stealing while the pitcher has been in the game, season to date. Only present if the player is the current pitcher.

#### <a name="defensemancatcherstolenbases">Stolen Bases - Catcher</a>

`c_sb` is the total number of players who have stolen a base on the catcher, season to date. Only present if the player is the current catcher.

#### <a name="defensemancatchercaughtstealing">Caught Stealing - Catcher</a>

`c_cs` is the total number of players who have been caught stealing by the catcher, season to date. Only present if the player is the current catcher.

3) As a child of the `<team>` element.

	<man pid="116539"/>
	
Here the `<man/>` element describes a single player in the team's lineup.

### Man Attributes - Team

+ [ID](#teammanid)

#### <a name="teammanid">ID</a>

`pid` is the ID number used for the player.

## <a name="edefense">Defense Element</a>

The `<defense>` element describes team information for the team last in the field.

	<defense type="home" id="nya">

### Defense Attributes

+ [ID](#defenseid)
+ [Type](#defensetype)

#### <a name="defenseid">ID</a>

`id` is the three-letter identifier used for the team. See all team codes [here](./team-information).

#### <a name="defensetype">Type</a>

`type` identifies if the team at bat is home or away. It has one of the following values:

+ `away`
+ `home`

## <a name="eball">Ball Element</a>

The `<ball/>` element describes the final ball in play. If a ball was not put in play by the final batter, the element is empty.

### Ball Attributes

+ [Batter](#ballbatter)
+ [Pitcher](#ballpitcher)
+ [Type](#balltype)
+ [X Coordinate](#ballxcoordinate)
+ [Y Coordinate](#ballycoordinate)

#### <a name="ballbatter">Batter</a>

`batter` is the ID number used for the batter.

#### <a name="ballpitcher">Pitcher</a>

`pitcher` is the ID number used for the pitcher.

#### <a name="balltype">Type</a>

`type` identifies the result of the pitch. It has one of the following values:

+ `S` -- Single
+ `D` -- Double
+ `T` -- Triple
+ `H` -- Home Run
+ `B` -- Bunt Groundout
+ `F` -- Flyout
+ `G` -- Groundout
+ `L` -- Lineout
+ `O` -- Pop Out

#### <a name="ballxcoordinate">X Coordinate</a>

`x` is the x coordinate where the pitch crossed the plate. See the explanation [here]().

#### <a name="ballycoordinate">Y Coordinate</a>

`y` is the y coordinate where the pitch crossed the plate. See the explanation [here]().

## <a name="elineup">Lineup Element</a>

The `<lineup>` element is a container element that does not have any attributes.

## <a name="eteam">Team Element</a>

The `<team>` element describes a single team.

	<team type="home" pitcher="121250" index="3">

### Team Attributes

+ [Index](#teamindex)
+ [Pitcher](#teampitcher)
+ [Type](#teamtype)

#### <a name="teamindex">Index</a>

`index` is unknown. It has one of the following values:

+ `1`
+ `2`
+ `3`
+ `4`
+ `5`
+ `6`
+ `7`
+ `8`
+ `9`

#### <a name="teampitcher">Pitcher</a>

`pitcher` is the ID number used for the pitcher.

#### <a name="teamtype">Type</a>

`type` identifies if the team is home or away. It has one of the following values:

+ `away`
+ `home`

## <a name="eweather">Weather Element</a>

The `<weather/>` element describes the weather for the game.

	<weather temp="84" condition="Sunny" wind="8mph Out To RF"/>
	
### Weather Attributes

+ [Condition](#weathercondition)
+ [Temperature](#weathertemperature)
+ [Wind](#weatherwind)

#### <a name="weathercondition">Condition</a>

`condition` is the game weather condition. It has one of the following values:

+ `Clear`
+ `Cloudy`
+ `Dome`
+ `Drizzle`
+ `Overcast`
+ `Partly Cloudy`
+ `Rain`
+ `Roof Closed`
+ `Snow`
+ `Sunny`

#### <a name="weathertemperature">Temperature</a>

`temp` is the temperature. It's not clear if this is *always* in Fahrenheit.

#### <a name="weatherwind">Wind</a>

`wind` is a text description of the wind movement.

## <a name="econtrol">Control Element</a>

The `<control/> element is unknown.

	<control wait="10" box="0"/>

### Control Attributes

+ [Box](#controlbox)
+ [Wait](#controlwait)

#### <a name="controlbox">Box</a>

`box` is unknown.

#### <a name="controlwait">Wait</a>

`wait` is unknown.
