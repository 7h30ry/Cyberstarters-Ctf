# Cyberstarters-Ctf

# SANITY CHECK

# Discord
![Discord](https://user-images.githubusercontent.com/51336409/235458307-32f46d31-36a5-4068-a210-8b316ddc8af0.png)

So, for this part I just followed the link the Discord cahnnel and i got this base64 string *RG9IQ1RGe3RyeV90b19iZV9oYWNrdGl2ZV9vbl9kaXNjb3JkX2hlaGVoZWhlaGVoZX0K*

So running this command *echo 'RG9IQ1RGe3RyeV90b19iZV9oYWNrdGl2ZV9vbl9kaXNjb3JkX2hlaGVoZWhlaGVoZX0K' | base64 -d*. I was able to get the flag "DoHCTF{try_to_be_hacktive_on_discord_hehehehehehe}"

# DoHCTF{_colwSPs:(}
![Screenshot_2023-05-01_09_34_23](https://user-images.githubusercontent.com/51336409/235458940-391c7304-14d7-43c1-af8b-55122c535f48.png)

This is really easy and quick, the flag has already been given, which is the name of the challenge, so the flag is "DoHCTF{_colwSPs:(}"

# Twitter
![Screenshot_2023-05-01_09_18_46](https://user-images.githubusercontent.com/51336409/235459330-7e656a38-ef32-4373-9785-cc8ff56b8bc2.png)

The flag for this is just Simply "Yes"


# WEB

# None Shall Pass
![Screenshot_2023-05-01_09_44_05](https://user-images.githubusercontent.com/51336409/235460203-60fe4967-5259-42e8-a99a-9623a3352d11.png)

Following the link *https://diaryofhackers-jwtvuln.chals.io/ink* We got to the website

Going to the websites cookie![Screenshot_2023-05-01_09_45_45](https://user-images.githubusercontent.com/51336409/235460434-ff29a3f1-f9a9-4a37-a315-1129cc5ce610.png)

I got this jwt Token *eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6Imd1ZXN0In0.iJ9U4tIUxxLbbOb_YXVkpvkBqtPsFtAxWIvmcakDfL0*

The token has three part(taking note of the dots) and they are all in Base64, but we are concerned with the first two which are:

# Base64                                                     # Decoded
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9                          {"alg":"HS256","typ":"JWT"}
eyJ1c2VybmFtZSI6Imd1ZXN0In0                                    {"username":"guest"}

So what we are going to do now is that we are going to do some changes which will look like this:

{"alg":"none","typ":"JWT"}
{"username":"admin"}

Now we base64 encode them back:
"eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0="
"eyJ1c2VybmFtZSI6ImFkbWluIn0="

Now that we have new enocded strings we join them together with dots, and we also remember the third part of the original token.
So the new token will looklike this:

"eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0=.eyJ1c2VybmFtZSI6ImFkbWluIn0=.iJ9U4tIUxxLbbOb_YXVkpvkBqtPsFtAxWIvmcakDfL0"

Replace it with the original token in the using the devtools. Then you get your flag
![Screenshot_2023-05-01_10_02_57](https://user-images.githubusercontent.com/51336409/235463374-0c1b9e21-3f9f-4a87-ba9a-d969be8c8e8c.png)
"DoHCTF{jwt_has_a_none_algo_loll}"


# OSINT

# Rogue Agent 
![Screenshot_2023-05-01_10_08_31](https://user-images.githubusercontent.com/51336409/235464165-06cb06cf-b1ab-4f88-b9de-50b1e73475c9.png)
 
 For this challenge we were provided with a phone number "+2348109439442". We are asked to find someone on LinkedIn whose third name is "Mustapha".
 After trying several Osint tools on the phone(i even tried using True caller) it did not yield anything. So i open my bank app and did as if i wanted to transfer some money to the phone number(Bank to PalmPay). Then i go the person's Which is "Adebayo Ekeh Mustapha". Then i went to LinkedIn to search for the name

![Screenshot_2023-05-01_10_16_06](https://user-images.githubusercontent.com/51336409/235466416-27a0ce5e-f536-4109-b522-0d330d80f352.png)

I got this Base64 from the profile "RG9IQ1RGe3RoYXRfd2FzX2Vhc3lfcmlnaHQ/X3JpZ2h0P30K" decoding it we got the flag "DoHCTF{that_was_easy_right?_right?}"
 




