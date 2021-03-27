# Linux

```
sudo fallocate -l 4G /swapfile Create a 4 gigabyte swapfile
sudo chmod 600 /swapfile Secure the swapfile by restricting access to root
sudo mkswap /swapfile Mark the file as a swap space
sudo swapon /swapfile Enable the swap
echo "/swapfile none swap sw 0 0" | sudo tee -a /etc/fstab Persist swapfile over reboots 
```

```
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
echo "/swapfile none swap sw 0 0" | sudo tee -a /etc/fstab
```


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

### new swap
```
sudo install -o root -g root -m 0600 /dev/null /swapfile
sudo dd if=/dev/zero of=/swapfile bs=1k count=2048k
sudo mkswap /swapfile
sudo swapon /swapfile
sudo echo "/swapfile       swap    swap    auto      0       0" | tee -a /etc/fstab
sudo sysctl -w vm.swappiness=10
echo vm.swappiness = 10 | tee -a /etc/sysctl.conf

```

Note: this article was originally published on Nov 21, 2013. It has been updated to ensure that the suggested changes
are still compatible
</pre>
## size of folder
```
sudo du -sh /var
```
