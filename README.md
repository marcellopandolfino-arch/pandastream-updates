# Panda Stream — aggiornamenti

Questo repository pubblico distribuisce il manifest degli aggiornamenti in-app di Panda Stream.

Manifest letto dall'app:
`https://raw.githubusercontent.com/marcellopandolfino-arch/pandastream-updates/main/update.json`

## Pubblicare il primo APK con aggiornamenti automatici

1. Apri il progetto `PandaStream_V54_AUTO_UPDATE_CONFIGURED.zip` in Android Studio.
2. Genera un APK **release firmato con la stessa chiave** usata per le versioni già distribuite.
3. In questo repository crea una GitHub Release con tag `v0.4.55`.
4. Carica il file come asset con nome esatto `PandaStream.apk`.
5. Verifica che l'URL indicato in `update.json` restituisca l'APK.

La configurazione iniziale in `update.json` è `versionCode: 56` e `versionName: 0.4.55`. Il link alla release non sarà scaricabile fino a quando l'asset APK non verrà effettivamente caricato.

## Pubblicare le versioni successive

Per ogni release:
- incrementa `versionCode` e `versionName` in `app/build.gradle.kts`;
- mantieni la stessa chiave di firma;
- carica l'APK firmato nella release GitHub con tag corrispondente e asset chiamato `PandaStream.apk`;
- aggiorna `update.json` con il nuovo codice versione, nome versione, URL dell'APK e note.

Esempio di URL per la versione 0.4.56:
`https://github.com/marcellopandolfino-arch/pandastream-updates/releases/download/v0.4.56/PandaStream.apk`

Non pubblicare nel manifest una versione prima che il relativo APK sia stato caricato e verificato.
