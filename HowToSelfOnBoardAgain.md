## Problem summary

When the user, alice, sign up with IBM Developer Portal for the first time.  She will receive an sign up activation link in her email, the link is valid for 72 hours by default.

What happen if the alice did not activate her account, this can be because email server is down, alice was on vacation and so on.

Currently, alice will not be able to onboard herself, nor reset the password.

## Solution

Pre-requite: When a portal is created with IBM API Connect, a Drupal administrator, admin, is created with that portal site.  The account hold the power to unlock the above user

- Login as portal administrator, admin, select `People`
<img width="621" alt="image" src="https://user-images.githubusercontent.com/24717424/217950241-c70a5c51-970d-47aa-b446-fa812c494f44.png">

- select the user in question, alice, and select appropriate action.  In this case, I choose `Cancel the selected user account(s)`
<img width="624" alt="image" src="https://user-images.githubusercontent.com/24717424/217950521-7241a372-8568-4e5d-85f6-c78d9fa76f38.png">

- Select the `Delete the account and its content ....` and `Confirm`
<img width="703" alt="image" src="https://user-images.githubusercontent.com/24717424/217950616-881ed273-a186-4731-818d-98e40633559e.png">

## Result

Alice can sign up again
