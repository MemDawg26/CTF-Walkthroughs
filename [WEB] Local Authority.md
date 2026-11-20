# [Easy] Web Exploitation - Local Authority
**Description:** Can you get the flag? Go to this website and see what you can discover.  
**Date Attempted:** 11/20/2026
***
## Walkthrough
- Step 1: My first step is to check how the login page handles potentially correct or incorrect credentials like admin/admin. When I put these incorrect credentials in, I am taken to a new page that just says: **"Log In Failed"**
- Step 2, my next step is to check the cookies and see if there are any potentially helpful pieces of information. There does not seem to be anything in my cookies panel.
- Step 3: At this point, I'm not 100% sure what to look at next, but I will look at the HTML itself to see if there are any clues, though I am not the greatest at understanding it. Looking at the HTML before attempting to log in does not seem to yield anything substantial. However, after the failed login, I can see in the body portion that secure.js is called immediately before the "Log In Failed" message.
- Step 4: Now looking at secure.js, there is a function named checkPassword that actually shows us that the credentials need to be `admin` and `strongPassword098765`.
- Step 5: Using these credentials, we are authenticated and brought to a page with the flag

**Flag:** academy{j5_15_7r4n5p4r3n7_df9583b6}
