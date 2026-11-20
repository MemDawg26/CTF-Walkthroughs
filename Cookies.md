# [Easy] Cookies
**Description:** Who doesn't love cookies? Try to figure out the best one.  
**Date Attempted: 11/20/2026**
***
**Walkthrough:**
- Step 1: Upon starting the instance, we are brought to a webpage to search cookies. My first step is to test how the page responds to different answers.
- Step 2: I test a legitimate cookie, and my favorite: ginger cookies. Well, this website doesn't think ginger cookies exist.
- Step 3: Next, I will try chocolate chip. Interestingly, the search appears to be case-sensitive, as Chocolate Chip give me an error message, while chocolate chip gives me a message that reads: **That is a cookie! Not very special though...**
- Step 4: Clearly, this webpage utilizes some background database, which may hint towards some sort of injection attack. But given the theme of the challenge, I am inclined to focus on cookies for now.
- Step 5: Let's inspect the page and see if the cookies gives us any useful information. I right-click on the page, select inspect, go to "Application" and click the cookies tab on the left-hand side under storage. While I have this cookie page open, I notice that any time a cookie(snack) does not exist, the cookie value is -1. For chocolate chip, the cookie value is 1. For peanut butter, the cookie value is 5. This makes me think that the cookies(snacks) are ranked through the cookie value.
- Step 6: Another thing I notice in the Inspect is that when searching, we are sending a POST request to http://xebec.cylabacademy.net:36800/search. An unsuccessful search keeps us on the main page, while a successful search sends a GET request to http://xebec.cylabacademy.net:36800/check and updates the cookie value. We may be able to exploit this to return us a cookie with the flag.
- 
