---
layout: post
title: "Docker DOOM"
excerpt: "Kill your running Docker container using Id's DOOM!"
tags: [docker, doom]
comments: true
image:
  feature: doomposthead.png
---

Tired of killing Docker containers by having to type in
`docker rm <docker_container>`? With every dull stroke of keys on the keyboard
you only wish that you could be saving earth from a possible invasion from
hell? Worry no longer! Now you can kill those Docker containers with the
proper tool, a rocket launcher (or BFG, or shotgun, or whatever)!

## Stop talking, I want to run this now

Download and place this binary on the machine running docker:

<div markdown="0"><a href="#" class="btn btn-info">dockerdoomd</a></div>

Startup a few docker containers e.g.,:

{% highlight css %}
for i in {1..2} ; do docker run -d -t ubuntu:14.04; done
{% endhighlight %}

Now run the downloaded docker binary:

{% highlight css %}
./dockerdoomd
{% endhighlight %}

You should receive output similiar to:

{% highlight css %}
╭─gideon@localhost  ~
╰─$ ./dockerdoomd
2015/01/24 16:50:50 Pulling image from public repo
Pulling repository gideonred/dockerdoom
f5abca9b93a3: Download complete
511136ea3c5a: Download complete
53f858aaaf03: Download complete
837339b91538: Download complete
615c102e2290: Download complete
b39b81afc8ca: Download complete
3972ba383c15: Download complete
90c7ac13f81e: Download complete
Status: Downloaded newer image for gideonred/dockerdoom:latest
2015/01/24 16:53:05 Image downloaded
2015/01/24 16:53:05 Trying to start docker container ...
2015/01/24 16:53:05 Waiting 5 seconds for "dockerdoom" to show in "docker ps". You can change this wait with -dockerWait.
PORT=5900
2015/01/24 16:53:10 Docker container started, you can now connect to it with a VNC viewer at port 5900
{% endhighlight %}

Get a VNC Viewer up and running. You could try [Chicken of the VNC](http://sourceforge.net/projects/cotvnc/).

Connect the VNC Viewer to the machine running `dockerdoomd` at port 5900. The password is `1234`.

<figure>
    <a href="/images/vncdockerdoomd.png"><img src="/images/vncdockerdoomd.png"></a>
    <figcaption><title="Chicken of the VNC viewer">Connecting Chicken of the VNC viewer to dockerdoomd</a>.</figcaption>
</figure>
