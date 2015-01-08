# jw-streamsense
JW player Comscore Stream Sense plugin bower component based on https://github.com/fcingolani/jw6ss

Usage
-----

Include JW player library

    <script src="../bower_components/jwplayer-mirror/jwplayer.js"></script>

Install JW player Stream Sense plugin

    $ bower install jw-streamsense

Include the .js files:

    <!-- StreamSense -->
    <script src='../bower_components/jw-streamsense/streamsense.min.js'></script>

    <!-- jw6ss library -->
    <script src='../bower_components/jw-streamsense/jw6ss.js'></script>

Setup UDM

    JW6SS.setupUdm("http://int.sitestat.com/X-company/X-project/s?");

Initialize JW6SS with observing all JW players

    JW6SS.observeAll();

Example for JW player 6+ using:
    var playerConfig = {
        primary: 'html5',
        controlbar: 'over',
        file: $("video").attr("src"),
        image: $("video").attr("poster"),
        width: "100%",
        streamsense: {
            loggingEnabled: false
        }
    };

    var playerItem  = jwplayer($("video")).setup(playerConfig);

    // Store player configuration in jwPlayer object (for jw6ss)
    playerItem.config = playerConfig;

    // Streamsense tracking with jw player plugin jw6ss
    JW6SS.setupUdm("http://int.sitestat.com/X-company/X-project/s?");
    JW6SS.observeAll();

