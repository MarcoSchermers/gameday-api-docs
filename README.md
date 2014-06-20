# Unofficial MLB Gameday API Documentation

The MLB Gameday API is a collection of XML files hosted on an [MLB server](http://gd2.mlb.com/components/game/mlb/). These files provide extensive game data and statistics for all Major League Baseball games. This is the same data that powers the Gameday web application and presumably the [At Bat](http://mlb.mlb.com/mobile/atbat/) mobile applications. The API includes the well-known Pitchf/x data (provided by the team at [Sportvision](https://www.sportvision.com/baseball/pitchfx)) as well as various game information (e.g. box score, scoring play, and event logs).

The MLB Advanced Media, L.P. ("MLBAM") has provided an explicit copyright for the data which you can read [here](http://gdx.mlb.com/components/copyright.txt) or in full below: 

> The accounts, descriptions, data and presentation in the referring page (the "Materials") are proprietary content of MLB Advanced Media, L.P ("MLBAM").  
Only individual, non-commercial, non-bulk use of the Materials is permitted and any other use of the Materials is prohibited without prior written authorization from MLBAM.  
Authorized users of the Materials are prohibited from using the Materials in any commercial manner other than as expressly authorized by MLBAM.

MLB has provided the data for what appears to be educational or research purposes. Adherence to the copyright as provided by MLBAM is the responsibility of the user.

The MLB Gameday API is public in its availability, however outside of the Pitchf/x data set, the API has not been publicly documented. The collection of files in this repository is the result of a humble attempt to analyze the files found within the API and provide insight to their data structure and content.

As with any first attempt, there may be missing or incomplete information. Due to the terse nature of naming choices, some assumptions have been made that may prove to be incorrect. In addition, there is a redundancy of information across several files with a known issue of inconsistent document language (semantics remain consistent). This is part of the documenting process and will be addressed at the appropriate time.  Known issues will be opened and the community may do the same. Amendments and suggestions are encouraged via pull requests.

Although this collection aspires to be "unofficial documentation", at this point it is not strict in its language as you would find in technical documentation (i.e. adherence to [RFC 2119](http://www.ietf.org/rfc/rfc2119.txt)). As with the document language inconsistencies, this will be addressed at the appropriate time. Until that point, consider this to be a collection of useful summaries in layman's terms.

# Author

[Brian M. Palma](https://twitter.com/brianmpalma), [brianmpalma@gmail.com](mailto:brianmpalma@gmail.com)

# License

This collection of documentation is available under the MIT License. The contents of the MLB Gameday API files are property of MLB and use is restricted to the limitations set forth in their [copyright](http://gdx.mlb.com/components/copyright.txt) seen above.