# scanview_server_exec

This contains the scanview server executable to run on the edison. This file should be transferred over to the edison with scp, and started with ssh or shell. You can start it with...

>>> ./scanview_server -port:13367 -ctrlmod_port:13366

where 13367 is the server's port and 13366 is ctrlmod's port, or with just

>>> ./scanview_server

In this case, the server will default to port 13367 and 13366. You can really use whatever ports you want - but when starting its important that they are specified when starting scanview_server if they are something other than default.

Once the server is running you can open scanview, make sure the port is correct in the settings, and connect. If it doesn't connect to ctrlmod right now that's fine, as long as it connects to the server program. You can then run the "setup server autostart" tool (the rightmost button on toolbar) to make it so that the server will always start when the edison is powered up.

Whatever ports were used when the server was started are the ports that will be used when the edison starts up from now on. The server will also start ctrlmod and ctrlmod will start scanning on startup right away. That way, when you power up the system both the server program and ctrlmod should start running with scan and navigation data being output.

There shouldn't be frequent updates to scanview_server, but when there are updates you have to manually copy the new version to replace the old version. With ctrlmod this is not necessary as scanview will be connected to scanview_server and can push new versions of that through scanview.
