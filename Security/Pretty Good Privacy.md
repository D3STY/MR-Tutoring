PGP (Pretty Good Privacy) ist eine Verschlüsselungssoftware, die verwendet wird, um die Datenschutz und sichere Kommunikation zwischen zwei Parteien zu schützen. Sie ermöglicht es den Benutzern, Daten und digitale Übertragungen sicher auszutauschen, indem sie Verschlüsselungs- und Entschlüsselungstools bereitstellt.

![https://darknetlive.com/images/pgp-encryption-3e6fcd95.jpeg](https://darknetlive.com/images/pgp-encryption-3e6fcd95.jpeg)

## PGP-Verschlüsselung

Um Verschlüsselung und Entschlüsselung bereitzustellen, verwendet PGP die Public-Key-Kryptografie. Die Public-Key-Kryptografie ist ein asymmetrisches Verschlüsselungsschema, das zwei verschiedene Schlüssel verwendet: den öffentlichen Schlüssel zur Verschlüsselung von Daten und den privaten Schlüssel zur Entschlüsselung.

Sie können Ihren öffentlichen Schlüssel frei mit anderen teilen, während Sie Ihren privaten Schlüssel geheim halten. Jeder mit Ihrem öffentlichen Schlüssel kann ihn verwenden, um Informationen zu verschlüsseln, die nur Sie mit Ihrem privaten Schlüssel entschlüsseln können.

Um PGP-Verschlüsselung zu verwenden, müssen Sie zunächst ein öffentliches und privates Schlüsselpaar mit einer PGP-Software generieren, wie z.B.

[Kleopatra](https://apps.kde.org/kleopatra/)

Anschließend können Sie Ihren öffentlichen Schlüssel mit anderen teilen, die ihn verwenden können, um Daten zu verschlüsseln, die sie Ihnen senden möchten.

So funktioniert die PGP-Nachrichtenverschlüsselung:

## Schlüsselerzeugung

Ein Benutzer generiert ein Schlüsselpaar, einen öffentlichen Schlüssel und einen privaten Schlüssel. Der öffentliche Schlüssel wird mit anderen geteilt, während der private Schlüssel geheim bleibt.

## Verschlüsselung

Um eine verschlüsselte Nachricht zu senden, verwendet der Sender den öffentlichen Schlüssel des Empfängers, um die Nachricht zu verschlüsseln. Dadurch kann nur der beabsichtigte Empfänger die Nachricht entschlüsseln.

## Entschlüsselung

Der Empfänger verwendet dann seinen privaten Schlüssel, um die verschlüsselte Nachricht zu entschlüsseln.

## Signieren

Für zusätzliche Sicherheit kann der Sender seinen privaten Schlüssel verwenden, um der Nachricht eine digitale Signatur hinzuzufügen. Die Signatur dient als Nachweis dafür, dass die Nachricht vom Eigentümer des Schlüssels verfasst und gesendet wurde.

## Verifizierung

Beim Empfang einer signierten Nachricht kann der Empfänger den öffentlichen Schlüssel des Absenders verwenden, um die digitale Signatur der Nachricht zu überprüfen. Eine gültige Signatur zeigt, dass die Nachricht vom Absender gesendet wurde und nicht verändert wurde. Selbst die geringste Änderung in der Originalnachricht, selbst nur ein Zeichen, führt zum Scheitern des Verifizierungsprozesses.

Hier ist eine Schritt-für-Schritt-Anleitung, wie Sie all dies mit Kleopatra durchführen können:

## Kleopatra herunterladen und installieren

Gehen Sie [hierhin](https://gpg4win.org/download.html)

und laden Sie den Installer für Gpg4win (GNU Privacy Guard für Windows) herunter. Kleopatra, ein Zertifikatsmanager für
[OpenPGP](https://www.openpgp.org/)
ist eine der enthaltenen Softwareanwendungen in Gpg4win.
Für Linux-Benutzer finden Sie Kleopatra[hier](https://apps.kde.org/kleopatra/)

![https://darknetlive.com/images/install-kleopetra-c3804fdd.jpeg](https://darknetlive.com/images/install-kleopetra-c3804fdd.jpeg)

## Installieren Sie Kleopatra

Installieren Sie das Programm und führen Sie es aus.

## Generieren Sie ein PGP-Schlüsselpaar

Sobald die Installation abgeschlossen ist, klicken Sie auf "Neues Schlüsselpaar erstellen".

![https://darknetlive.com/images/generate-keys-35da478d.jpeg](https://darknetlive.com/images/generate-keys-35da478d.jpeg)

### Generierung eines neuen Schlüsselpaars

Sie haben dann die Möglichkeit, einen Namen mit Ihrem öffentlichen PGP-Schlüssel zu verknüpfen. Sie können auch Ihre E-Mail-Adresse eingeben und Ihren Schlüssel mit einem Passwort schützen. Das Passwort stellt sicher, dass nur Sie Zugriff auf Ihren privaten Schlüssel haben.

![https://darknetlive.com/images/name-passphrase-f08451a1.jpeg](https://darknetlive.com/images/name-passphrase-f08451a1.jpeg)

Geben Sie Ihren Namen, Ihre E-Mail-Adresse und Ihr Passwort ein

Klicken Sie auf "OK" in der Erfolgsmeldung.

Schlüssel erfolgreich erstellt

Doppelklicken Sie als Nächstes auf das Zertifikat, das Sie gerade erstellt haben, und klicken Sie dann auf "Exportieren".

![https://darknetlive.com/images/export-key-e2c68438.jpeg](https://darknetlive.com/images/export-key-e2c68438.jpeg)

### Exportieren Sie Ihren öffentlichen Schlüssel

Dies öffnet ein Popup mit Ihrem öffentlichen Schlüssel. Sie können ihn kopieren, speichern und mit anderen teilen.

![https://darknetlive.com/images/public-key-f6f9221e.jpeg](https://darknetlive.com/images/public-key-f6f9221e.jpeg)

### Der öffentliche Schlüssel

Sie können die Zeilen, die mit "Kommentar" beginnen, löschen, wenn Sie die Informationen nicht mit anderen teilen möchten.

## Importieren von öffentlichen Schlüsseln

Um Nachrichten zu verschlüsseln, die Sie an andere senden, müssen Sie deren PGP-öffentliche Schlüssel importieren.

Kopieren Sie den öffentlichen Schlüssel, den Sie importieren möchten, und fügen Sie ihn in den Notepad ein.

![https://darknetlive.com/images/begin-import-ae14f723.jpeg](https://darknetlive.com/images/begin-import-ae14f723.jpeg)

### Beginnen Sie den Importvorgang

Klicken Sie als Nächstes auf "Tools", dann auf "Clipboard" und anschließend auf "Zertifikat importieren".

![https://darknetlive.com/images/import-key-021a21f7.jpeg](https://darknetlive.com/images/import-key-021a21f7.jpeg)

### Zertifikat importieren

Klicken Sie im Popup auf "Zertifizieren". Die auf dem folgenden Popup angezeigten Informationen können Ihnen dabei helfen, sicherzustellen, dass Sie den richtigen öffentlichen Schlüssel importieren.

Klicken Sie auf "Zertifizieren" und anschließend auf "OK" im nächsten Popup.

![https://darknetlive.com/images/complete-import-1f5c84b1.jpeg](https://darknetlive.com/images/complete-import-1f5c84b1.jpeg)

## Eine Nachricht verschlüsseln

Kopieren Sie die Klartextnachricht, die Sie importieren möchten, und fügen Sie sie in den Notepad ein.

![https://darknetlive.com/images/encrypt-92bdc534.jpeg](https://darknetlive.com/images/encrypt-92bdc534.jpeg)

### Beginnen Sie die Verschlüsselung

Klicken Sie dann auf "Tools", dann auf "Clipboard" und anschließend auf "Verschlüsseln". Klicken Sie im Popup auf "Empfänger hinzufügen".

Wählen Sie dann den öffentlichen Schlüssel aus, mit dem Sie die Nachricht verschlüsseln möchten, und klicken Sie auf "OK".

![https://darknetlive.com/images/encryption-complete-79ad3afb.jpeg](https://darknetlive.com/images/encryption-complete-79ad3afb.jpeg)

### Verschlüsselung abgeschlossen

Die verschlüsselte Nachricht wird in Ihrer Zwischenablage gespeichert. Sie sollten sie so versenden, wie sie ist, an den beabsichtigten Empfänger.

## Eine Nachricht entschlüsseln

Um eine mit Ihrem PGP-öffentlichen Schlüssel verschlüsselte Nachricht zu entschlüsseln, fügen Sie die gesamte Nachricht unverändert in den Notepad ein. Klicken Sie dann auf "Decrypt/Verify Notepad".

![https://darknetlive.com/images/decrypt-message-d2c5e523.jpeg](https://darknetlive.com/images/decrypt-message-d2c5e523.jpeg)

### Eine mit Ihrem öffentlichen Schlüssel verschlüsselte Nachricht entschlüsseln

Der Entschlüsselungsvorgang wird nur erfolgreich sein, wenn die Nachricht mit Ihrem öffentlichen Schlüssel verschlüsselt wurde.

## Eine Nachricht signieren

Fügen Sie die Nachricht, die Sie signieren möchten, im Notepad ein. Klicken Sie dann auf "Empfänger". Durch Deaktivieren der Kontrollkästchen "Für mich verschlüsseln" und "Für andere verschlüsseln" wird eine unverschlüsselte Nachricht erstellt.

![https://darknetlive.com/images/sign-message-11ccb506.jpeg](https://darknetlive.com/images/sign-message-11ccb506.jpeg)

### Signieren Sie eine Nachricht mit Ihren Schlüsseln

Klicken Sie als Nächstes auf "Sign Notepad". Die signierte Nachricht wird im Notepad angezeigt, sobald die Signatur erfolgreich ist.

![https://darknetlive.com/images/message-signed-721e042e.jpeg](https://darknetlive.com/images/message-signed-721e042e.jpeg)

## Überprüfen einer signierten Nachricht

Um eine signierte Nachricht zu überprüfen, müssen Sie den öffentlichen Schlüssel des Absenders importiert haben.

Fügen Sie die Nachricht in den Notepad ein.

![https://darknetlive.com/images/verify-signed-message-bb0a0035.jpeg](https://darknetlive.com/images/verify-signed-message-bb0a0035.jpeg)

### Signierte Nachricht überprüfen

Klicken Sie auf die Registerkarte "Decrypt/Verify Notepad", um die Nachricht zu überprüfen.

![https://darknetlive.com/images/signature-verified-3251ef86.jpeg](https://darknetlive.com/images/signature-verified-3251ef86.jpeg)

Die Nachricht wird erfolgreich überprüft, wenn die Signatur gültig ist.

Im Wesentlichen sichert PGP-Verschlüsselung die Kommunikation, indem sie:

- Die Modifikation und Abfangen von Daten während der Übertragung verhindert.
- Gewährleistet, dass die übertragenen Daten vor unbefugtem Zugriff geschützt sind.
- Empfängern ermöglicht, die Authentizität der Absender zu überprüfen.

Es ist entscheidend, private Schlüssel sicher aufzubewahren, um die Integrität des Verschlüsselungsprozesses zu gewährleisten. Denken Sie daran, Ihre Schlüssel zu sichern und die Backups zu schützen.