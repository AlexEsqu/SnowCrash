We set up the VM in virtualbox with a passthrough for port 4242.
We launched ssh from WSL but it couldn't connect. After a couple tries we switched to cmd on windows and managed to connect.

We arrived in level00's home, which only contained a README. It says:
"Hiro Protagonist. Last of the freelance hackers. Or so he thinks."
We looked at the hidden files with `ls -la`. There was nothing out of the ordinary: a seemingly default .bashrc, a .bashhistory, a .cache

We did a couple global searches with find to get all files that could be read, but it ended up giving a lot of seemingly useless results in /usr/lib
We grepped for "flag" among those but there was no interesting match.

Back in the home, we saw that .cache contains a file named "motd.legal-displayed", but which is empty.




# IDA Dissasembly of hiro

Main calls parse_policy_file("/etc/snowcrash/hiro.conf", &v10), file does not exist, should exit but instead uses partially initialized default structure

