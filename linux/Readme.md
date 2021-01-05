# Linux
<pre>
To check current values using these commands:

sudo cat /proc/sys/vm/swappiness
sudo cat /proc/sys/vm/vfs_cache_pressure
To enable these settings without rebooting use the following commands:

sudo sysctl -w vm.swappiness=10
sudo sysctl -w vm.vfs_cache_pressure=200
 
</pre>
## How To Add Swap on Amazon Linux EC2
<pre>
Of course, on low-memory instances swap is wise. To add a 1GB swap file for example, from command line you’ll type:

sudo dd if=/dev/zero of=/swapfile bs=1024 count=1048576
Now setup the swap file with the command:

sudo mkswap /swapfile
sudo chmod 600 /swapfile
Now enable the swap:

sudo swapon /swapfile
If you use the top command, you should now see the 1gb swap added. So now lets make swap persistent so it’s not
dropped when you reboot. Edit /etc/fstab file and add this line as the last line:

/swapfile swap swap defaults 0 0

When you reboot, use the free -h or df -h command to check for swap.

Remember, adding swap can help save your server from running out of memory but if it’s already using a big chunk 
of swap (aka swapping), that is never good for performance. A lot can be expanded upon with regards to swap and paging/swapping. However, the point today is that stripping/tuning the AMI.

Note: this article was originally published on Nov 21, 2013. It has been updated to ensure that the suggested changes
are still compatible
</pre>
