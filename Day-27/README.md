# Day 27 - My Def for SOC Analyst Challenge

Welcome to day 27 of the 30-day My Def for SOC Analyst challenge, which is a challenge that I created for the sole purpose of helping aspiring SOC analysts obtain practical experience in 30 days. If you're interested in following along with this challenge, I would highly recommend that you pause the video and start from day one if you haven't done so already. 

By the end of this video, you'll learn how to investigate an RDP Brute Force alert and what are some of the things that you can look for. Let's get started!

## Investigating RDP Brute Force Attacks

When it comes to investigating RDP Brute Force attacks, we can pretty much do the same thing that we did for our SSH Brute Force attack. It's a different protocol, but the same methodology will apply. 

First and foremost, head over to your web GUI and click on the hamburger icon. From there, scroll down and click on **Alerts** under **Security**. Now, depending on your data, you may or may not have a lot of alerts, but do make sure that your time frame is set to 30 days. I have a total of 414 alerts, but I do have six alerts that are RDP Brute Force. 

So, what I'll do is just click on the filter, and this will filter for only RDP Brute Force alerts. Scrolling down, I'll select the first one, which is this one right here that triggered on **15:15:52 on August 14th** and click on the **View Details** icon just to see a little bit more information here. I see the source IP of **81.1.163.2041** and it was using the username of **administrator**, and there were six events. 

Now, if you recall in our SSH alert, we did modify the alert to automatically create a ticket within OS Ticket, so let's do the same for our RDP Brute Force. 

Since I'm lazy, I'll go ahead and open up my rules and copy my SSH Brute Force alert. So, I'll click on **Edit Rule Settings**, go over to **Actions**, and let's just copy the body here. Now I'll click on my detection rules and select **RDP Brute Force**. Head over to **Edit Rule Settings**, go into **Actions**, click on **Web Hook**, and my OS Ticket should automatically be selected. I'll paste in my body here and then save changes. 

What I'll also do is click on **Edit Rule Settings**, go over to **Schedule**, and make sure that it is running every 1 minute. 

## Investigation Process

Now, if I go over to my notepad, whenever we're investigating Brute Force attacks, I want to know four things: 

1. Is the IP known to perform Brute Force activity?
2. Are any other users affected by the IP?
3. Were any of them successful?
4. If so, what activity occurred after the successful login?

Now, if I take a look at the alert, we see that the IP is this **81.1.163.2041**. I'll go ahead and copy that and paste it into my notepad. It is targeting **administrator**.

### Check IP Reputation

To find out about the first question, I'll be using **AbuseIPDB** and **GreyNoise**. Checking **AbuseIPDB**, we see that this IP was reported 55 times and has a confidence of abuse of 48%. It is stemming from the country of **Russia**, and at the bottom, we do get reports of application RDP Brute Force where the username is **administrator**.

Now, let's check out **GreyNoise**. We do see this IP classified as **unknown intent**. It says GreyNoise has identified scanning activity from this IP; however, we cannot determine its intent. It is still considered internet background noise since it is scanning the entire internet and not targeting you specifically.

Clicking on **Next Suggested Actions**, as long as you're not running software vulnerable to the activity captured by GreyNoise, you can probably close out the alert. It also gives you the reason for the close, and that is why I absolutely love GreyNoise whenever I'm performing an investigation that has an IP address.

Looking at the tags, we can see it's an **RDP crawler**, so that's pretty cool. If you log in, you can get additional information, but this should be enough. Simply by taking a look at our **AbuseIPDB** and looking at **GreyNoise**, we can see that this IP is associated with RDP activity. 

So, yes, the first question is answered. 

### Check Affected Users

The second question: Are any other users affected by this IP? Let's head over to our Discover and make sure our time frame is set to 30 days. I'll copy out the IP address and hit enter. Within 30 days, we get 245 events. Now if I search for the field name of **user.name**, we can see that it's 100% this **administrator** account. 

So, answering number two, are any other users affected by this IP? No, only **administrator**.

### Check Successful Authentications

Now, were any of them successful? This is very important. If you recall, successful authentications will generate an event code of **4624** under security. With that being said, I'll type in **event.code:4624**, and there are no results matching my search criteria. Just to make sure that my query works as expected, I am going to remove everything except for my event code, and yes, I do get some hits: **148**. So that means that my query was actually correct and there were no successful authentications from this particular IP address. 

What this means is that we're pretty safe. Were any of them successful? No. 

### Activity After Successful Login

If so, what activity occurred after the successful login? Well, nothing because none of it was successful. 

Now, if you recall in our previous video when we went over our **Mythic C2**, we did Brute Force our RDP server, and I did capture that IP address, which was actually **181.215.182.51**. 

So this was the IP I was using to Brute Force our target server. Now, if I were to do the same checks, for example, is this IP known to perform Brute Force activity? Well, let's take a look using **AbuseIPDB**. This was reported seven times with a confidence of abuse of 25%. Scrolling down, it says **DoS attack**, **Brute Force**, **web spam**, **bad web bot**, and that's about it. 

So we do know that this IP is known to perform some nefarious activities. 

What about **GreyNoise**? This particular IP address would be quite interesting because it was not observed by **GreyNoise**. Take a look at what it says: **GreyNoise has not observed this IP mass scanning the internet within the past 90 days.** If your organization has observed this IP, it is likely targeting your organization, industry, or software stack, and that is why I'm interested. 

So if I click on **I am interested in this IP**, we can now create an alert for this particular IP by using **GreyNoise**. Again, **GreyNoise** is an absolutely amazing tool. 

But let's go back down to our questions here: 

- Is this IP known to perform Brute Force activity? Kind of, but I will say yes because by using **AbuseIPDB**, it was reported for Brute Force. 

- Any other users affected by this IP? Well, let's take a look. I already searched for this particular IP, and it gave me 106 events. Clicking on **username**, we can see two user accounts. The first one is **administrator**, and the second one is a computer account. 

We know this is a computer account because it ends in a dollar symbol. Honestly, we aren't really too worried about host accounts at least for now, but instead, what we want to look for are actual user accounts whenever we're performing this particular check, which in our case only **administrator** was targeted. 

So the answer will be no; only **administrator**.

Now, were any of them successful? Let's do an **event.code:4624**, and uh-oh, we have three events. So that means there was definitely a successful logon. 

Now we can say, were any of them successful? Yes. 

If so, what activity occurred after the successful logon? Well, that is a great question. Now we can start jotting down exactly what time the successful logon occurred. In our case, it was **August 12th, 2024, at 19:56:15**.

Now, if you're like me, you might be wondering what time zone this is, and that's a great question. To determine the time zone, you want to click on the hamburger icon and scroll down, click on **Stack Management**, and at the bottom under **Cabbana**, click on **Advanced Settings**. From here, we can see the time zone; the default time zone is set to the browser, and honestly, we don't want that. Instead, we want **UTC**, so I'll click on **Save Changes** and reload the page.

Now let's go over to our Discover, and you might notice that my time doesn't change, and that's because on my laptop itself it is set to UTC. But if it was set to, let's say, **Eastern Standard**, then this timestamp should change accordingly. In fact, let's do a test. I'll go over to **Advanced Settings**, change this to **US Eastern**, hit **Save**, and reload. 

Yes, the time should change now. So I do recommend that you go ahead and do that for your environment as well. 

Anyhow, the successful login occurred on **August 12th, 2024, at 19:56:15 UTC**, and after the login, it says there was administrative privileges assigned. 

So just like that, we can tie everything back to our RDP Brute Force attack, where we were able to find successful logins and notate that it was due to the usage of **Crowbar** for the RDP Brute Force attack.

## Conclusion

That will conclude today's video for day 27 of our SOC Analyst challenge. I hope you learned a little something about investigating RDP Brute Force alerts. 

Join me tomorrow as we cover the next topic, and thanks for following along in this journey!

