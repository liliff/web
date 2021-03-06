+++
title = "kyoto.maidlab.jp"
date = 2012-06-25T07:30:00Z

[extra]
updated = 2013-02-25T21:22:00Z

[taxonomies]
categories = ["projects"]
+++
**Notice**: If you're here to find information about maidlab.jp, this is 
the wrong place. Maidlab.jp is a top level domain name whose use is shared 
through the non-profit DNS hosting services at afraid.org. I know nothing 
more than that, but thanks for visiting.

**Second Notice (2013.06.29)**: Yes, the maintainer of maidlab.jp stealthed 
his domain on afraid.org. No, I don't know the reason behind it. That said, 
these links are mostly broken.

So, over this weekend I've set up kyoto.maidlab.jp to point to this 
server. I'm going to start using this virtual host for my own projects, I 
suppose. Right now, I've made a pretty front page in just a matter of 
minutes, and just today I've set up some form of a public upload site using 
restricted SSH. I've wrote a script to make the whole set-up and upload 
process not too difficult, but enough to prevent automated spam bots.

This is basically how I set it up and use it, though the instructions differ:

    [liliff@hicari ~]$ wget -qO - http://kyoto.maidlab.jp/kmjp.sh > ./bin/kmjp
    [liliff@hicari ~]$ chmod +x ./bin/kmjp
    [liliff@hicari ~]$ kmjp bin/kmjp 
    Downloading private key...
    Private key now stored at /home/liliff/.ssh/kmjp-upload.
    Uploading bin/kmjp...
    kmjp                                      100% 1419     1.4KB/s   00:00    
    Success! Uploaded file can be found at:
    http://kyoto.maidlab.jp/p/kmjp

Pretty neat, isn't it? I'm basically giving access to SCP for anyone for a 
particular folder on the server. The major flaw I have right now is that 
files may be overwritten, which is something I'll be looking into resolving 
server-side. It's also somewhat amusing how the script itself auto-updates 
should there be a change on the server's version of the script. Useful.

Update (9:17): It's been updated to use rsync instead of scp now, to get 
around the overwriting files issue.

Update (16 Feb 2013): This didn't turn out to be very safe to unleash to 
the public. I wrote [an article that goes into detail about public scp][]. 
As a result, the above script and associated private key are no longer available 
for download.

[an article that goes into detail about public scp]: @/logs/2013-02-16-using-scp-to-provide-a-public-upload-service.md
