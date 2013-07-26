---
layout: post
title: Timelapse images on OS X with Wacaw
---

Step 1: Download wacaw from http://webcam-tools.sourceforge.net/

Step 2: Get the list of available devices with `./wacaw -L`. Note the device
and input number you want to use.

Step 3: save the script below as `timelapse.sh` and run it!

{% highlight bash %}
#!/bin/bash

interval=${1:-30}

echo "Starting to take pictures every ${interval} seconds."

while true
do
    prefix=$(date +%Y-%m-%d:%H:%M:%S)
    # allow 10 frames for the camera to adjust brightness
    # use appropriate device/input based on Step 2 above
    ./wacaw --png -x 1280 -y 720 -n 10 -d 3 -i 0 img-${prefix}
    echo "Saved img-${prefix}.png"
    sleep ${interval}
done

{% endhighlight %}
