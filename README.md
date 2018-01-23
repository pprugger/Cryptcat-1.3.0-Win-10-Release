# Cryptcat-1.3.0-Win-10-Release

Dear fellow!

I changed cryptcat so it compiles on Windows 10 with Visual Studio 2017.
Please be aware that it compiles, but i didn't test it very well.
If you have bug reports please write me on github or to pruggi@abwesend.de

Best regards pprugger



Usage:

connect to somewhere:   cryptcat.exe [-options] hostname port[s] [ports] ...
listen for inbound:     cryptcat.exe -l -p port [options] [hostname] [port]

options:

        -d              detach from console, background mode
        -g gateway      source-routing hop point[s], up to 8
        -G num          source-routing pointer: 4, 8, 12, ...
        -h              this cruft
        -i secs         delay interval for lines sent, ports scanned
        -k key          secret key to use for encryption
        -l              listen mode, for inbound connects
        -L              listen harder, re-listen on socket close
        -n              numeric-only IP addresses, no DNS
        -o file         hex dump of traffic
        -p port         local port number
        -r              randomize local and remote ports
        -s addr         local source address
        -t              answer TELNET negotiation
        -u              UDP mode
        -v              verbose [use twice to be more verbose]
        -w secs         timeout for connects and final net reads
        -z              zero-I/O mode [used for scanning]
        port numbers can be individual or ranges: m-n [inclusive]


Code changes:

File: NETCAT.c
Commented lines 1704 to 1745
Created new code after this block, because i just don't like this behavior.
If the program is started without arguments now the help will be displayed.
Without my changes the arguments can also be inserted AFTER the program was started.

File: doexec.c
Line 440
Changed RecvBuffer to Buffer
RecvBuffer is not existent in the whole project, also in none of the Libraries.
Out of the codeflow i assumed it should be Buffer.

File: twofish2.cpp
A few counter variables were not declarated as int, added it. 


The whole project is compiled WITHOUT the GAPING_SECURITY_HOLE define!
If you want to compile it with the define go to:
Project -> Settings -> C/C++ -> Preprocessor -> Preprocessor definitions 
and add 
GAPING_SECURITY_HOLE


