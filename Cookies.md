# [Easy] Cookies
**Description:** Who doesn't love cookies? Try to figure out the best one.  
**Date Attempted: 11/20/2026**
***
## Walkthrough
**Testing Inputs**
- Step 1: Upon launching the challenge, we are taken to a webpage that allows us to search for cookies(which I will refer to as treats from here on out). I first want to see how the page reacts to different inputs. When I type in `chocolate chip`, I get a green message that says: ***That is a cookie! Not very special though...*** If I put in Thin Mints, I get a red error message that says: ***That doesn't appear to be a valid cookie.*** On the surface, this doesn't mean a whole lot.
- Step 2: Next, we take a look at the cookies(of the webpage). Right click on the page, click Inspect, go to the Application tab, select Cookies in the storage section on the left-hand side. When I load into the webpage, it appears that my cookie value it set to -1. When I guess an unsuccessful treat, it appears that my cookie value stays -1. If I guess `snickerdoodle`, my cookie is set to 0. If I guess `chocolate chip`, my cookie value is set to 1. If I guess `peanut butter`, my cookie value is set to 5. This tells me that our webpage responds differently based on what the treat is, and the cookie value may play a role.
- Step 3: Next thing I wanted to check was where our traffic was really going. In Inspect, I go to the Network Tab and see that there is a POST request to **http://xebec.cylabacademy.net:18270/search** and a GET request to **http://xebec.cylabacademy.net:18270/check**. I am able to look at the response to the GET request and we can see the HTML for the webpage. So now, I'm curious to see how this response payload may change based on the cookie value.

*Note:* At this point, I was pretty much stuck, as I was not sure how to efficiently analyze the response of cookie values because I thought it would require me to know a bunch of treat names, and I couldn't think of any more successful ones. So I did some researching and came across Burp Suite. I had heard of this before, but I had never used it, so I opted to try it out. This same process can be done using a python script, though I must admit I was unable to get it to work.

Burp Suite allows you to collect web traffic and automate requests, and in turn be able to analyze the responses to the requests. The following steps were completed in Burp Suite Community Edition:
***
**Burp Suite Intruder**
- Step 4: In Burp Suite, we need to collect network traffic. First, in the Proxy tab, I turn on Intercept mode.
- Step 5: Next, we need to open a Burp Suite browser and go to the website given by the challenge. You will need to click `Forward` in the Proxy tab for the page to load.
- Step 6: Then, I type in a successful cookie name, and press forward twice. The first one accounts for the POST, and the second for the GET.
- Step 7: Under the Proxy tab, select the HTTP History sub-tab and scroll down to the bottom of the list of web traffic. Right click and select `Send to Intruder`.
- Step 8: In the Intruder tab, find the Cookie: name=<number> field in the GET request. Highlight the number with your mouse and click `Add§` next to Position. This will allow Burp Suite to insert different cookie values there, which is how we will be able to analyze the different response bodies. In the Payload area to the right, make sure Simple List is selected. Then, you will need to add values to the payload list. I chose to keep it small by putting in 1 through 25. Press add for each number.
- Step 9: On the right side of the screen, go into the Settings tab and scroll until you find Grep - Match. Select the checkbox next to "Flag responses matching these expressions". Clear the list and add `academy{`. Grep is a tool that finds/grabs a specified selection of text, and adding "academy{" will allow us to find the flag easier.
- Step 10: Click `Start Attack`. You should see a new window open that shows the progress of the attack. For each number in your payload list, Burp will set that number as the cookie value. You should see varying value for response length. Eventually, you should see a 1 in the `academy{` column, which corresponds to payload 18.
- Step 11: Click on the line where payload is 18. You should see the Request and Response boxes. Underneath both of them is a search bar. In the response, search for the beginning of our flag: `academy{`. You should eventually see the flag.

**Flag**: academy{3v3ry1_l0v3s_c00k135_90a3a7cb}
