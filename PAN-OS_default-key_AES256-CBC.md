# PAN-OS - Default master key

## Encryption level below 2 (i.e., AES-256-CBC)

### Decrypt recipe
```
From_Base64('A-Za-z0-9+/=',true,false)
AES_Decrypt({'option':'Hex','string':'8103850245b9b48f0428c5b74e2615528103850245b9b48f0428c5b74e261552'},{'option':'Hex','string':'0000000000000000000000000000000'},'CBC','Raw','Raw',{'option':'Hex','string':''},{'option':'Hex','string':''})
```
### Encrypt recipe
```
AES_Encrypt({'option':'Hex','string':'8103850245b9b48f0428c5b74e2615528103850245b9b48f0428c5b74e261552'},{'option':'Hex','string':'0000000000000000000000000000000'},'CBC','Raw','Raw',{'option':'Hex','string':''})
To_Base64('A-Za-z0-9+/=')
```

### Example data
```
6M1Jh9EsdCK58ui82LGVrA==
```
extracted from:
```
# show shared server-profile ldap
bind-password -AQ==x9274bKW29DwT+bg1eDbQ+k3lg0=6M1Jh9EsdCK58ui82LGVrA== 
```
