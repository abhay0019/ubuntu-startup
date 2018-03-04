

Changes done in ~/.bashrc

In between comment :-

# ABHAY SINGH'S BASH PLAYY .... STAY AWAYYY





#BELOW SHITS IS NOT WORKING :( for system startup and shutdown :`( 


#a

Put all your executing code in a separate text file with an arbitrary name such as foo.sh and save it in an arbitrary place.
Add

#!/bin/sh
as first line of your code.
Try executing your foo.sh by

sudo foo.sh
to check there are no errors at all.
Provide your /etc/rc.local script with full path and name of your created script after the sh command
sh '/path/to/your/script/foo.sh'
Remember to put the above line before the last line of code

exit 0
at the end of the /etc/rc.local script.
Check first line of /etc/rc.local to be
#!/bin/sh -e
Make your /etc/rc.local executable in case it is not already executable by
sudo chown root /etc/rc.local
sudo chmod 755 /etc/rc.local
Check everything works fine by executing
sudo /etc/init.d/rc.local start
Test restart your system.
#a

for system startup  changes in ..

/etc/rc.local

for system shutdown ..

/etc/rc0.d/K99_shutdown(scrip_to_run)


for system restart ..

/etc/rc6.d/K99_restart


	
To execute a script at shutdown or reboot:

save your script in /etc/rc6.d
Make it executable: sudo chmod +x K99_script
Notes:

The script in rc6.d must be with no .sh extension
The name of your script must begin with K99 to run at the right time.
The scripts in this directory are executed in alphabetical order.

# ubuntu-startup
