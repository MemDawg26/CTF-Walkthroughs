# [Easy] Web Exploitation - Old Sessions
**Description:** Proper session timeout controls are critical for securing user accounts. If a user logs in on a public or shared computer but doesn’t explicitly log out (instead simply closing the browser tab), and session expiration dates are misconfigured, the session may remain active indefinitely. This then allows an attacker using the same browser later to access the user’s account without needing credentials, exploiting the fact that sessions never expire and remain authenticated.

Your friend tells you to check out a new social media platform he built a few years ago. Although its still under development, he said the site is almost complete. He also mentioned that he hates constantly logging into sites, and so has made his page that 'once you login, you never have to log-out again'!

**Date Attempted:** 11/20/2026
***
## Walkthrough
- Step 1: The link brings us to a simple website login with an option to register an account. My first check is to see how the website may respond to credentials like admin/admin. While inspecting the cookies and network traffic, nothing was really substantial.
- Step 2: I register an account using simple credentials, and after logging in, there is a page with 4 messages from various users. One message says: "Hey I found a strange page at /sessions"
- Step 3: I edit the web address by adding /sessions to the end of it and I am brought to a page holding the session information. There are two sessions, mine that I had just created, and a session for an account named admin.
- Step 4: In the cookies section of Inspect, I replace my session key with the session key of the admin and attempt to go back to the main dashboard page.
- Step 5: I now have access to the admin account, which also provides me the flag above the messages!

**Flag:** academy{s3t_s3ss10n_3xp1rat10n5_3b59378b}
