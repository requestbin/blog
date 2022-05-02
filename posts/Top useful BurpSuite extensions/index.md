Burp Suite is an intercepting HTTP Proxy, and it is the defacto tool for performing web application security testing.  Burp is highly functional and provides an intuitive and user-friendly interface. Its proxy function allows configuration of very fine-grained interception rules, and clear analysis of HTTP messages structure and contents. The proxy can also be configured to perform automated matching and replacement of message headers, and provides an in-browser interface for viewing the proxy cache and reissuing individual requests.

Below we’ve listed out the top extensions which are top useful for the hacking and bugbounty:

# Logger++
Burp Suite Pro allows you to proxy every request and response you put through it. But there are occasions when you need to see more. What is Burp Scanner, or a particular extension doing behind the scenes, for instance?

Well, whether you're debugging an issue, or just want to take a closer look at what Burp Suite is doing, Logger++ gives you what you need. It stores all Burp's requests and responses in an easily exported and sortable table.

* Link: https://portswigger.net/bappstore/470b7057b86f41c396a97903377f3d81

# ActiveScan++
ActiveScan++ extends Burp Suite's active and passive scanning capabilities. Designed to add minimal network overhead, it identifies application behavior that may be of interest to advanced testers.

* Link: https://portswigger.net/bappstore/3123d5b5f25c4128894d97ea1acc4976

![ảnh](https://user-images.githubusercontent.com/10446854/166291324-37553015-9206-4dbb-873d-928a321455c3.png)

# Autorize Burp
Autorize is an extension aimed at helping the penetration tester to detect authorization vulnerabilities—one of the more time-consuming tasks in a web application penetration test.

* Link: https://portswigger.net/bappstore/f9bbac8c4acf4aefa4d7dc92a991af2f

# Turbo Intruder

Simple to use and eminently stable, Burp Intruder is a powerful bruteforcing tool. But for some tasks, you really can't have enough power. Enter: Turbo Intruder. Built for speed using a custom HTTP stack, and configured in Python, Turbo Intruder is blisteringly quick. In fact, it's capable of making tens of thousands of HTTP requests per second, if necessary.

Turbo Intruder is great for finding race conditions, as well as performing complex attacks involving multiple steps, or signed requests, for example. It's highly configurable and is designed to achieve flat memory use - so it can run for days if it has to. If you're half-decent in Python and this sounds like fun, we highly recommend taking Turbo Intruder for a spin.

* Link: https://portswigger.net/bappstore/9abaa233088242e8be252cd4ff534988

# J2EEScan

Straight out of the box, Burp Scanner can find a whole host of vulnerabilities. But there's always room for improvement - especially if you're operating in any type of a niche. If you find yourself testing applications that make use of J2EE on a regular basis, then J2EEScan is for you.

J2EEScan adds a catalogue of over 40 J2EE-specific vulnerabilities to Burp Scanner's automated pentesting repertoire. This is a great add-on that expands Burp Suite Pro's web vulnerability scanning capabilities into a useful new area.

* Link: https://portswigger.net/bappstore/7ec6d429fed04cdcb6243d8ba7358880

# Backslash Powered Scanner
Vulnerability scanners are great, but there are cases where there's no substitute for human deductive reasoning, right? Well, yes and no. Don't forget that scanners can do many things a human alone can't. There's really no replacement for either. Backslash Powered Scanner bridges this gap and helps pentesters find interesting items to investigate manually.

It does this by mimicking human intuition. As a result, it can detect many bugs traditional scanners would miss. Some of these are known; others will be completely novel. It's not a panacea - items marked as "interesting" do then require manual attention. But still, Backslash Powered Scanner is a potent tool in the hands of expert Burp Suite users.

* Link: https://portswigger.net/bappstore/9cff8c55432a45808432e26dbb2b41d8

# Upload Scanner

Web applications allowing users to upload their own files is a classic cause for concern in penetration testing. If users are allowed to upload files in a risky manner, there are myriad ways it can be exploited. This means that file upload functions can take some time to evaluate - time most pentesters don't have to waste.

Upload Scanner is a pentesting tool that could save you a lot of time. It has the ability to upload a number of different file types, laced with different forms of payload. Upload Scanner can test for vulnerabilities including server-side request forgery (SSRF) and XML external entity (XXE) injection using common file types like JPEG, PDF, and MP4 as vectors.

* Link: https://portswigger.net/bappstore/b2244cbb6953442cb3c82fa0a0d908fa

# JSON Beautifier
JSON is many things, but in its compressed state, "beautiful" isn't one of them. How often have you intercepted a response including data set in scrunched-up JSON and let out a sigh? Given that JSON is used in more or less everything nowadays, you'll be pleased to know that this beautifier tool makes it much easier to work with in the pentesting context.

![ảnh](https://user-images.githubusercontent.com/10446854/166290711-25630970-be31-48a5-8f93-5913e19e694f.png)

# AuthMatrix
We already mentioned Autorize (#2), which is a simple tool for speeding up testing of user access control functions. AuthMatrix made our list because it's a really useful - if slightly more complex - addition to this setup.

AuthMatrix gives pentesters a simple matrix grid to define the desired levels of access privilege within an organization/web app. It then tests each function for different types of user. One of AuthMatrix's best features is a "chain" mode, which enables cross-site request forgery (CSRF) tokens to be grabbed from requests and attached to subsequent attempts.

* Link: https://portswigger.net/bappstore/30d8ee9f40c041b0bfec67441aad158e

# Param Miner
That's right: a third extension from PortSwigger's very own James Kettle. You could accuse us of bias - but hear us out first. There's a reason James's tools are so popular. The idea for this one came back when he was initially researching web cache poisoning. He needed a way to quickly find unkeyed inputs - and so Param Miner was born. It finds hidden parameters that can be used for just about any purpose.

* Link: https://portswigger.net/bappstore/17d2949a985c4b7ca092728dba871943

# Upload Scanner
Web applications allowing users to upload their own files is a classic cause for concern in penetration testing. If users are allowed to upload files in a risky manner, there are myriad ways it can be exploited. This means that file upload functions can take some time to evaluate - time most pentesters don't have to waste.

Upload Scanner is a pentesting tool that could save you a lot of time. It has the ability to upload a number of different file types, laced with different forms of payload. Upload Scanner can test for vulnerabilities including server-side request forgery (SSRF) and XML external entity (XXE) injection using common file types like JPEG, PDF, and MP4 as vectors.

* Link: https://portswigger.net/bappstore/b2244cbb6953442cb3c82fa0a0d908fa
A simple tool, JSON Beautifier gives you the option to either "beautify" or "minify" (crunch back up) your target's JSON content. All of this takes place within Burp Suite. This is the most popular download in the BApp store, and it makes life as a pentester much easier. We love it.
