# Rassegna News Naviros – regole

Le news del sito vivono in `news.json` (chiavi `it` ed `en`, stessa struttura). `index.html` le carica al volo; non toccare `index.html`.

Struttura di un giorno:
{"d":"6 nov 2026","items":[{"t":"Titolo","b":"Corpo: cosa è successo, numeri, e la frase 'Perché conta: ...'","s":"Nome fonte","u":"https://..."}]}
In `en` la data è "6 Nov 2026" e testo in inglese.

Regole:
- I giorni sono in ordine decrescente: il nuovo giorno va IN TESTA all'array.
- Solo operazioni con almeno una fonte apribile (BeBeez, Il Sole 24 Ore, Milano Finanza, Forbes Italia, Teleborsa, ANSA, comunicati societari, report KPMG/EY/BCG/PEM/AIFI). Niente rumor senza fonte.
- Priorità al mid-market italiano (target tra 3 e 100 mln di fatturato), poi operazioni grandi se rilevanti per il mercato.
- 1-4 notizie per giorno. Se non c'è nulla di verificabile, non aggiungere il giorno.
- Ogni corpo: 2-4 frasi di fatti (chi, cosa, quota, valore se noto, closing/annuncio) + "Perché conta:" con una lezione per chi vende o compra. Mai copiare frasi dalla fonte.
- Non inventare valori: se il prezzo non è pubblico, dirlo.
- Non duplicare notizie già presenti (controlla titoli e URL).
- Il JSON deve restare valido (verificare con `python3 -c "import json;json.load(open('news.json'))"`).
- Aggiornare `<lastmod>` in `sitemap.xml` con la data del giorno.
