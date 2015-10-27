+++
Categories = ["Development"]
Description = "Making Phantomjs 2.0 work with AWS EC2"
Tags = ["Development", "Phantomjs", "AWS", "EC2"]
date = "2015-10-18T18:17:35+02:00"
menu = "main"
title = "Phantomjs 2.0 on EC2 instance"

+++

## What's this all about?

I've been working on a project that uses phantomjs v1.9.x to output a PDF report.  Because of the seemingly unrelated vunerabilities to SSL due to the [POODLE attacks](https://en.wikipedia.org/wiki/POODLE) attacking a vunerability in TLS v1.0-1.2 meaning I needed to upgrade to TLS v2.0 if I still want to use a secure https connection... which isn't supported in phantomjs v1.9.x

### So, what does that all mean?

That means that phantomjs stops working if you upgrade your https certificate!  There is some hope though with phantomjs v2.0, this new release uses the new QT and webkit library (which does support the new encryption).  Phantomjs 2.0 binary is available to [download](http://phantomjs.org/download.html) for windows and mac, but no Linux!  As we are running on AWS EC2 instances and using the default AMI based on redhat there is no binary already compiled... 

### What?  So what happens now?

You can download the source and follow the [build instructions](http://phantomjs.org/build.html) to build on your version of linux.  I've compiled a binary to work on the amazon AMI for your convenience you can [download here](https://github.com/TheSmokingGnu/compiledPhantomjsBin.git) this should save you pretty much a day compiling.

### Phew, so... we done now?

If only... phantomjs v2.0 is pretty new so expect many bugs... I'm sure they will be fixed at some point, and it's open source so you can fix it yourself.  I was battling a while with [this](https://github.com/ariya/phantomjs/issues/12685)  You may find your own battle.  I only hope this speeds you up a little bit and the karma comes back to me one day :)