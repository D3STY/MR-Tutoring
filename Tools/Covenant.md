- Run container with Docker:
	- `docker run -it -p 7443:7443 -p 80:80 -p 443:443 -p 8443:8443 --name covenant -v /Users/alh4zr3d/Tools/Covenant/Covenant/Data:/app/Data covenant --username Alh4zr3d --computername 0.0.0.0`
	- Self-signed certificate
		1. `openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -sha256 -days 365 -nodes`
		2. PFX: `openssl pkcs12 -export -in cert.pem -inkey key.pem -out cert.pfx`
		2. DER: `openssl x509 -pubkey -outform der -in cert.pem -out cert.cer`

 - Obfuscation
	 - 