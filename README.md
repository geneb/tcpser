This is a fork of Jim Brain's tcpser serial to IP bridge program.
The original source code can be found here:
http://www.jbrain.com/pub/linux/serial/

My changes are based upon the rc12 archive dated 11Mar09.

This version includes two new features.
1. You can specify an ip address and a port using the -p command line switch.
   This allows using a specific ip address on a system that has more than
   one network interface.
   The format is "-p <ip addr>:<port>" - both elements should be specified.

2. Upon connect, tcpser will issue the IAC WILLDO ECHO command sequence to 
   the remote end.  
   What this does is tell the remote telnet client that the host will handle
   character echo.  "raw" telnet clients like those found shipped with Linux
   and Windows require this, otherwise they'll echo typed characters and you
   end up with ddooubblliinngg characters.

I've done a _little_ cleanup of the warnings generated by -Wall.  Most of
these seem to be the result of using unsigned char * when the prototype
of the called function (most often standard library calls) calls for char *.

As of 02Mar16, the only testing done is to make sure it compiles. :)  I don't
have the ability to properly test the code at this time, so I depend on you,
dear downloader, to build and test this thing. :)
 
