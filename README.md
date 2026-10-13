# Panda Stream — aggiornamenti

Questo repository pubblico distribuisce il manifest degli aggiornamenti in-app di Panda Stream.

Manifest letto dall'app:
`https://raw.githubusercontent.com/marcellopandolfino-arch/pandastream-updates/main/update.json`

## Prima release con updater: versione 0.4.55

- Apri il progetto `PandaStream_V54_AUTO_UPDATE_NEW_KEY_READY.zip` in Android Studio.
- In **Build → Generate Signed Bundle / APK… → APK → Next → Create new…**, crea un nuovo keystore di release.
- Conserva il file keystore e le password in modo sicuro. Non caricare mai la chiave privata su GitHub né inviarla in chat.
- Poiché la nuova firma è diversa dalle vecchie build, gli utenti devono disinstallare la vecchia app prima di installare questa versione. La disinstallazione può cancellare dati locali, incluse preferenze e credenziali memorizzate.
- Pubblica l'APK firmato nella GitHub Release con tag `v0.4.55`, asset chiamato esattamente `PandaStream.apk`.
- Il manifest iniziale contiene `versionCode: 56` e `versionName: 0.4.55`; il popup non appare alla prima installazione perché l'app è già alla versione del manifest.

## Pubblicare gli aggiornamenti successivi

Per ogni release:
- incrementa `versionCode` e aggiorna `versionName` in `app/build.gradle.kts`;
- riutilizza sempre lo stesso keystore, alias e password della prima release con updater;
- carica l'APK firmato in una GitHub Release con tag corrispondente e asset chiamato `PandaStream.apk`;
- solo dopo aver verificato il download dell'APK, aggiorna `update.json` con il nuovo codice versione, nome versione, URL dell'APK e note.

Esempio di URL per la versione 0.4.56:
`https://github.com/marcellopandolfino-arch/pandastream-updates/releases/download/v0.4.56/PandaStream.apk`

Non aggiornare il manifest prima che l'APK sia stato pubblicato. Per provare il popup, crea una seconda build firmata con lo stesso keystore e un `versionCode` superiore (es. 57), caricala prima della modifica del manifest, quindi aggiorna il manifest. Non perdere mai il keystore: senza di esso le build future non potranno aggiornare normalmente le installazioni.
