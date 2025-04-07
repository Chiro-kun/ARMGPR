# Guya.moe Manga Hosting Guide

Questa guida ti aiuterà a ospitare una serie manga su Imgur utilizzando Guya.moe. Seguendo questi passaggi, potrai organizzare più capitoli sotto un unico link per una serie, rendendo più facile la navigazione per i lettori.

## Indice

1. [Introduzione](#introduzione)
2. [Prerequisiti](#prerequisiti)
3. [Caricamento su Imgur](#caricamento-su-imgur)
4. [Configurazione iniziale](#configurazione-iniziale)
5. [Aggiunta di ulteriori capitoli](#aggiunta-di-ulteriori-capitoli)
6. [Conclusione](#conclusione)

## Introduzione

Guya.moe è un sito che permette di leggere manga online. Questa guida è stata creata per aiutare gli utenti a ospitare i propri manga su Imgur e integrarli con Guya.moe, fornendo un'esperienza di lettura fluida e organizzata. Alcune parti di questa guida sono tratte dalla guida di u/Kawaii_Loli_Imouto.

## Prerequisiti

- Un account Imgur
- Un account GitHub
- Capitoli del manga pronti per essere caricati

## Caricamento su Imgur

1. Assicurati di aver creato un account Imgur e un account GitHub.
2. Esporta i capitoli del manga in una cartella e ordina/zeropad i nomi dei file correttamente.
3. Vai su Imgur e clicca sul pulsante verde "New post" in alto a sinistra. Poi clicca su "Choose Photo/Video" e naviga fino alla cartella contenente le immagini.
4. Seleziona l'ultima immagine del capitolo, tieni premuto il tasto Shift e clicca sulla prima immagine del capitolo. Nel campo "file name" in basso, dovresti vedere i nomi dei file nell'ordine corretto.
5. Clicca su "open" e aspetta che i file vengano caricati. Dopo il caricamento, dai un nome alla tua galleria (puoi scegliere tra community o hidden).
6. Ripeti questi passaggi per tutti i capitoli che desideri ospitare.

## Configurazione iniziale

1. Vai su GitHub e clicca sul pulsante verde "New" in alto a sinistra. Dai un nome al repository e assicurati che sia pubblico (puoi saltare la sezione "initialize this repository with:"). Crea il repository.
2. Clicca su "creating a new file" nella sezione di configurazione rapida. Dai al file un nome che non cambierai (ogni volta che cambi il nome, cambierà anche il link URL).
3. Nel campo "edit the new file" incolla il seguente codice:

```json
{
  "title": "<manga title>",
  "description": "<manga description>",
  "artist": "<manga artist>",
  "author": "<manga author>",
  "cover": "<mangacoverurl.jpg>",
  "chapters": {
    "<chapter number>": {
      "title": "<chapter name>",
      "volume": "<volume number>",
      "groups": {
        "<group name>": "/proxy/api/imgur/chapter/<imgur id>/"
      },
      "last_updated": "1616368746"
    },
  }
}
```

4. Compila tutti i campi contrassegnati con <>. Per il campo ```<imgur id>```, vai su Imgur e prendi l'ID Imgur (la stringa alfanumerica dopo imgur.com/a/ nell'URL) del primo capitolo che desideri ospitare e incollalo. Dopo aver fatto questo, rimuovi l'ultima virgola nel codice e clicca su "commit new file".
5. Torna al file, clicca su "raw" e copia l'URL. Vai su cubari.moe, incolla l'URL. Questo sarà il link permanente per la tua serie manga (finché non cambi il nome del file su GitHub).

## Aggiunta di ulteriori capitoli

1. Torna al codice GitHub che hai scritto in precedenza e modificalo (icona a forma di matita).
2. Reinserisci la virgola dopo la parentesi graffa subito sotto "last updated".
3. In una nuova riga sopra le ultime due parentesi graffe, incolla il seguente codice e modifica i campi per corrispondere alle informazioni del capitolo che stai aggiungendo (assicurati di cambiare l'ID Imgur per corrispondere al capitolo):

```json
"<chapter number>": {
  "title": "<chapter name>",
  "volume": "<volume number>",
  "groups": {
    "<group name>": "/proxy/api/imgur/chapter/<imgur id>/"
  },
  "last_updated": "1616368746"
},
```

4. Ripeti questo passaggio per ogni capitolo che desideri aggiungere.
5. Una volta finito con tutti i capitoli, rimuovi l'ultima virgola alla fine del codice e clicca su "commit changes".
6. Quando torni al tuo URL di Guya.moe, dovrebbe essere aggiornato con i nuovi capitoli.
