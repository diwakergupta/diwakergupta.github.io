---
layout: post
title: Listing checkstyle violations using mvn
---

When you run `mvn checkstyle:check`, it will either succeed or fail if you
have any checkstyle violations. And when it fails, it unfortunately doesn't
print the violations and their locations by default. Here's a convenient
snippet to do this:

{% highlight bash %}
#!/bin/bash
mvn checkstyle:checkstyle \
    --quiet \
    -Dcheckstyle.enable.files.summary=false \
    -Dcheckstyle.enable.rules.summary=false \
    -Dcheckstyle.enable.severity.summary=false \
    -Dcheckstyle.enable.rss=false \
    -Dcheckstyle.output.file=/dev/stdout \
    -Dcheckstyle.output.format=plain
{% endhighlight %}
