# inning_hit.xml

The inning_hit.xml file provides information about balls in play. It consists of the following elements:

+ [`<hitchart>`](#ehitchart)
+ [`<hip/>`](#ehip)

These elements form the following structure:

    <hitchart>
        <hip/> # multiple elements
    </hitchart>

## <a name="ehitchart">Hitchart Element</a>

The `<hitchart>` element is a container element that does not have any attributes.

## <a name="ehip">Hit In Play Element</a>

The `<hip`> element describes a single ball in play.

    <hip des="Home Run" x="34.14" y="62.25" batter="116539" pitcher="456034" type="H" team="H" inning="3"/>

### Hit In Play Attributes

+ [Batter](#hipbatter)
+ [Pitcher](#hippitcher)
+ [Inning](#hipinning)
+ [Team](#hipteam)
+ [Type](#hiptype)
+ [Description](#hipdescription)
+ [X Coordinate](#hipxcoordinate)
+ [Y Coordinate](#hipycoordinate)


#### <a name="hipbatter">Batter</a>

`batter` is the ID number used for the batter.

#### <a name="hippitcher">Pitcher</a>

`pitcher` is the ID number used for the pitcher.

#### <a name="hipinning">Inning</a>

`inning` is the inning when the ball in play occurred.

#### <a name="hipteam">Team</a>

`team` identifies the team that put the ball in play. It has one of the following values:

+ `A` -- Away
+ `H` -- Home

#### <a name="hiptype">Type</a>

`type` identifies the outcome of the ball in play. It has one of the following values:

+ `O` -- Out
+ `H` -- Hit
+ `E` -- Error

#### <a name="hipdescription">Description</a>

`des` is a description of the ball in play. It may have one of the following values:

+ `Single`
+ `Double`
+ `Triple`
+ `Home Run`
+ `Groundout`
+ `Lineout`
+ `Flyout`
+ `Pop Out`
+ `Bunt Groundout`
+ `Bunt Lineout`
+ `Bunt Pop Out`
+ `Error`
+ `Field Error`
+ `Catcher Interference`
+ `Batter Interference`
+ `Runner Interference`
+ `Fan interference`
+ `null`

#### <a name="hipxcoordinate">X Coordinate</a>

`x` is the plotted X coordinate on a 250 x 250 image of the ballpark. See below for more information.

#### <a name="hipycoordinate">Y Coordinate</a>

`y` is the plotted Y coordinate on a 250 x 250 image of the ballpark. See below for more information.

#### (X, Y) Coordinate Note

According to an [article](http://indiemaps.com/blog/2009/07/visualizing-mlb-hit-locations-on-a-google-map/) from [Zachary Johnson](http://indiemaps.com/) about visualizing MLB hit locations on a Google Map,

> The hit location data recorded by MLB is reported in pixels. The employees watching the games plot locations on a 250×250 image of the ballpark; the (0,0) origin is — not home plate — but simply the upper left corner of the image.
