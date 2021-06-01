# iPerf-notes

A few helpful ways to test connectivity and bandwidth in a measured/consistent way.
Personally use this to troubleshoot network issues in ESXi specifically between hosts or out to Internet.


If testing internally, run a server on a VM:
iperf.exe -s

Or if testing out to public, setup a server in another physical location ideally, where the traffic has to traverse the Internet.

Run the client

Internal
iperf3.exe -c [server] -V -b 100M -P 20 --logfile filename1.log
iperf3.exe -c [server] -V -b 100M -P 20 -R --logfile filename2.log

External
iperf3.exe -c [server] -V -b 100M -P 5 --logfile filename1.log
iperf3.exe -c [server] -V -b 100M -P 5 -R --logfile filename2.log
