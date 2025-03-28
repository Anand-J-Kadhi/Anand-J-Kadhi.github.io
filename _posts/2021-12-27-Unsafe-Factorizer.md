---
layout: post
title: Atomicity
categories: [Technical, Java]
tags: [concurrency]
---

This is an excerpt collected from the book "Java Concurrency in practice"

![Java-Concurrency-In-Pracice-book]({{ site.baseurl }}/assets/image/jcip.jpg)

There is a hit counter which measures the number of requests processed. The obvios approach is to add a long field to the servlet and increment it on each request , as shown in UnsafeCountingFactorizer

{% highlight java %} @NotThreadSafe public class UnsafeCountingFactorizer implements Servlet { private long count=0;

public long getCount(){return count;}

public void service(ServletRequest req,ServletResponse resp){
    BigInteger i=extractFromRequest(req);
    BigInteger[] factors=factor(i);
    ++count;
    encodeIntoResponse(resp,factors);
}
} {% endhighlight %}


