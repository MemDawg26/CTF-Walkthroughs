# [Easy] Web Exploitation - Cookie Monster Secret Recipe
**Description:** Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?  
***
**Walkthrough**  
- Step 1: Upon launching the instance, we are brought to a web page that takes a username and password.
- Step 2: The first thing I try is testing admin/admin to see how the webpage interacts with slightly random, and likely incorrect, credentials.

The webpage displays the following message:  

**Cookie Monster says: 'Me no need password. Me just need cookies!'**  
**Hint: Have you checked your cookies lately?**

- Step 3: This is a clue for us to check the cookies of the page, which we can find by right clicking on the page, selecting "Inspect", and going to the "Application" tab
- Step 4: On the left hand side, we select the "Cookies" tab under Storage, and we can see the cookie named "secret_recipe". We are give the value: **YWNhZGVteXtjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzM0RUYyQ0U4fQ%3D%3D** or the URL-decoded version **YWNhZGVteXtjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzM0RUYyQ0U4fQ==**
- Step 5: We need to completely decode this. Using the URL-decoded version, I copy and paste the string into CyberChef and use the Magic operation, which automatically provides potential solutions to decoding the string. Many of them give the same output, which just so happens to be our flag

**Flag:** academy{c00k1e_m0nster_l0ves_c00kies_34EF2CE8}
