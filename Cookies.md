# [Easy] Cookies
**Description:** Who doesn't love cookies? Try to figure out the best one.
***
- Step 1: Upon starting the instance, we are brought to a webpage to search cookies. My first step is to test how the page responds to different answers.
- Step 2: I test a legitimate cookie, and my favorite: ginger cookies. Well, this website doesn't think ginger cookies exist.
- Step 3: Next, I will try chocolate chip. Interestingly, the search appears to be case-sensitive, as Chocolate Chip give me an error message, while chocolate chip gives me a message that reads: **That is a cookie! Not very special though...**
- Step 4: Clearly, this webpage utilizes some background database, which may hint towards some sort of injection attack. But given the theme of the challenge, I am inclined to focus on cookies for now.
- Step 5: Let's inspect the page and see if the cookies gives us any useful information. I right-click on the page, select inspect, go to "Application" and click the cookies tab on the left-hand side under storage. 
