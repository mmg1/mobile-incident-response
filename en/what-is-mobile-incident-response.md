# Chapter 1: Mobile Incident Response

This chapter will explore the basic concepts behind incident response including a brief history, the IR process, how to account for mobile technologies and common incidents you are likely to encounter.

# [Chapter 1](chapter1.md) What is Mobile Incident Response

## [Chapter 1](part1/history.md) A brief history of incident response
On November 2, 1998, Robert Tappan Morris released the first worm on the Internet (dubbed the Morris Worm) and became part of computer security history by:

1. Unleashing the first large scale denial-of-service (DoS) attack on the Internet
2. Impacting an estimated (and refuted) 10% of computers on the Internet at that time (6,000 impacted)
3. Being the first person prosecuted under the Computer Fraud and Abuse Act (CFAA)

The impact to the Internet plus the significant challenges in coordinating a response is such a distributed environemtn led to the creation of the Computer Emergency Response Team Coordination Center (CERT/CC) by DARPA in 1988.[^1] The [CERT/CC](https://cert.org/) flourishes today and is part of the  Software Engineering Institute at Carnegie Mellon University. 

## [Chapter 1](part2/defining.md) Defining Incident Response

The goal of incident response is to quickly contain and mitigate incident. It's helpful to provide a more formal definition of incident response ("IR"):

>Incident response is an organized approach to addressing and managing the aftermath of a security breach or attack (also known as an incident). The goal is to handle the situation in a way that limits damage and reduces recovery time and costs. An incident response plan includes a policy that defines, in specific terms, what constitutes an incident and provides a step-by-step process that should be followed when an incident occurs. [^2] 

Over the past 3 decades, the process of incident response has matured. Bruce Schneier, a respected security technologist, wrote about evolution and future of IR in his popular [Schneier on Security](https://www.schneier.com/blog/archives/2014/11/the_future_of_i.html) [^3] blog. He identified broad focuses in each decade since the 1990s starting with protection, then moving into detection and finally focused on response by the 2010s.

He reflected that in recent years, new IR products and services are being developed and implemented due to three important trends:

1. Devices and data now regularly reside outside the control of IT departments (mobile, cloud, etc.)
2. Attack and threats are far more sophisticated and effective
3. Companies continue to under-invest protection and detection, increasing the need for response

The trend of companies under-investing in security is, unfortunately, a clear reality in mobile. 

*** Insert stats on insecure mobile apps ***

This amplifies the need for mobile incident response as the technology and data is clearly distributed, generally outside the control of IT and have a large number of security and privacy flaws.


## [Chapter 1](part3/process.md) Incident Response Process

The [SANS Institute](https://www.sans.org/) has defined 6 key IR steps in their book [Computer Security Incident Handling: Step-by-Step](http://www.amazon.com/Computer-Security-Incident-Handling-Step-/dp/0972427376/ref=sr_1_1?ie=UTF8&qid=1436392071&sr=8-1&keywords=Computer+Security+Incident+Handling%3A+Step-by-Step):

1. Preparation
2. Identification
3. Containment
4. Eradication
5. Recovery
6. Lessons learned

While we will cover this topic extensively in the chapter [Framework for Mobile Incident Response](mobile-incident-response-framework.md) and build upon frameworks from both SANS and NIST.

### Digital Forensics and Incident Response

Incident response is closely connected with forensics as nearly every incident requires the collection, storage and analysis of digital evidence.  This is a topic the authors and NowSecure employees have written about extensively since 2011:

1. [Android Forensics: Investigation, Analysis and Mobile Security for Google Android](http://www.amazon.com/Android-Forensics-Investigation-Analysis-Security/dp/1597496510) by Andrew Hoog
2. [iPhone and iOS Forensics: Investigation, Analysis and Mobile Security for Apple iPhone, iPad and iOS Devices](http://www.amazon.com/iPhone-iOS-Forensics-Investigation-Analysis/dp/1597496596/ref=pd_bxgy_14_img_y) by Katie Strzempka and Andrew Hoog
3. [Hacking and Securing iOS Applications: Stealing Data, Hijacking Software, and How to Prevent It](http://www.amazon.com/Hacking-Securing-iOS-Applications-Hijacking/dp/1449318746/ref=sr_1_1?s=books&ie=UTF8&qid=1433593160&sr=1-1&keywords=Hacking+and+Securing+iOS+Applications) by Jonathan Zdziarski
3. [Android Security Cookbook](http://www.amazon.com/Android-Security-Cookbook-Keith-Makan/dp/1782167161/ref=sr_1_1?s=books&ie=UTF8&qid=1433593041&sr=1-1&keywords=Android+Security+Cookbook) with co-author Scott Alexander-Bown
4. [Android Hacker’s Handbook](http://www.amazon.com/Android-Hackers-Handbook-Joshua-Drake/dp/111860864X/ref=sr_1_1?s=books&ie=UTF8&qid=1433593102&sr=1-1&keywords=Android+Hacker%E2%80%99s+Handbook) with co-author Pau Oliva Fora

As you explore mobile incident response more thoroughly, these books can provide far deeper technical details on mobile forensics and security.

## [Chapter 1](part4/mobileirvstraditional.md) How is mobile IR different than traditional computers-focused IR?

While the generalized incident response process should largely not need to change to incorporate new technologies, there are unique properties of mobile devices and operating systems that pose unique challenges.

### Individual Consumer Technology

Mobile devices, unlike computers and servers, were built for individual consumers. Since individuals by definition are not concerned with managing a large number of devices, many key IT management and security requirements were not built into the devices.

Notably, individual and enterprises do not have administrative (root) access to the devices. Can't monitor. Can't develop nearly as effective tools. Race2root. 

Oh, and the OS developers, OEM and wireless carriers all have the ability to get system/root access with their preinstalled apps so tons of other have access, just not you or the enterprise. And check out some of the things they do (Samsung keyboard flaw? 100s of other examples?)

Put my Learn to Love the Root spiel here? 

Mention that we can't do effective mobile app security testing without root (thx Apple)?  And recognize that attackers have pretty much always found ways to get root?

Lack of visibility and tools on these devices means that an enormous amount of our data is being extracted (and often done insecurely) and the people most impacted (the individuals and the enterprises they interact with as employees or customers) have no effective visibility to this happening.

### Application Sandbox

Define application sandbox, mobile architecture

Installable applications, due to the sandbox, cannot truly protect the device due to security restrictions. This made nearly all previously  PC-based approaches to security ineffective:

* Anti-virus / Anti-malware
* DLP
* ... 

### Explosive Growth

*** show chart from Ben Evans we use in our decks ***
The security industry didn't have time to mature given the explosive growth, and amplified by the new architecture and sandbox limitations.

### Connected Devices

Unlike laptops and desktops, mobile devices are almost always connected to the Internet.  They are rarely greater than 6 feet from their owner (even at night...try to find that study).  They connect to both mobile and Wi-Fi networks and other technologies exist such as bluetooth.

*** The average mobile phone (based on NS data) connected to 160 IP address a day and N countries. Show some data on where traffic is going, how much is encrypted, etc? ***

### Large Attack Surface

Mobile devices have a large attack surface. *** include mobile attack graph we have ? ***
*** Include the mobile exploitation graph we have? ***
*** include graph we have with # of actors involved in mobile devices? ***

We will explore these differences in depth in the [Attacking Mobile Devices](mobile-attacks.md) chapter.


### App store model

Do you remember when we used to install applications via CD-ROM? 3.5in floppy disks? 5 1/4? Further back than that? :-D

Well, today we generally take for granted that the App Store model has drastically changed how we install software and who develops that software.

The barrier of entry is much lower...anyone could be writing these apps. Big companies (who hopefully invest in security and QA but often don't), individuals or small companies intent to develop the next killer app or even amateurs or malicious parties that now have an incredibly effective delivery engine.

*** The average Android device in the US ships with ___ # of apps pre-installed. You can't uninstall many of them. You can disable many of them. Many of them have security and privacy flaws ***

It has never been easier to install an application on a computing device.

These differences ultimately add up sufficiently to create a paradigm shift from traditional computer-based IR.

# [Chapter 1](chapter1.md) Common Mobile Incidents
There are a number of common scenarios you will encounter when it performing IR for mobile devices:

* Internal investigation
* Malware discovered
* Device acting suspiciously

# [Chapter 1](chapter1.md) Running reference notes

- http://www.cert.org/incident-management/csirt-development/csirt-faq.cfm?

# [Chapter1](chapter1.md) Citations

Let's mimic what [Wikipedia does for citations](http://en.wikipedia.org/wiki/Robert_Tappan_Morris#References). We can use their style (MLA?) and then either the ^1 approach for a footnote or just the id in brackets. The disadvantage is we might have to manually re-number links. I'm open to other ideas!

[^1]: http://www.ietf.org/rfc/rfc2350.txt (appendix c)
[^2]: Rouse, Margaret. "What Is Incident Response?" SearchSecurity. TechTarget, Inc, Sept. 2005. Web. 03 June 2015. <http://searchsecurity.techtarget.com/definition/incident-response>
[^3]: Schneier, Bruce. "The Future of Incident Response" Schneier on Security. Nov. 2014. Web. 08 July 2015. <https://www.schneier.com/blog/archives/2014/11/the_future_of_i.html>
[^4]: http://www.amazon.com/Computer-Security-Incident-Handling-Step-/dp/0972427376/ref=sr_1_1?ie=UTF8&qid=1436392071&sr=8-1&keywords=Computer+Security+Incident+Handling%3A+Step-by-Step