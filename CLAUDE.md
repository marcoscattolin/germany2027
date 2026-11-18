# Germany 2027 – Viaggio in camper Milano → Berlino → Milano

Repository di lavoro per pianificare il viaggio in camper in Germania dell'estate 2027.
Lingua di lavoro: **italiano** (l'utente è madrelingua italiano; rispondere nella lingua dell'ultimo messaggio).

## Vincoli del viaggio

- **Partenza e rientro:** Milano (serve un **anello**, non un'andata semplice).
- **Date:** dal 20 al 30 agosto (11 giorni).
- **Obiettivo:** il giro deve arrivare a **Berlino**.
- **Limite giornaliero:** massimo **150 km/giorno**, con al massimo **2 giorni di eccezione**.
- **Gruppo:** 3 famiglie, 3 camper, bambini tra 9 e 12 anni → privilegiare attività per ragazzi (parchi, grotte, canoa, zoo, musei interattivi), tappe corte e pomeriggi liberi.
- **Distanze:** vanno calcolate con **Google Maps**, non stimate.

## Stato della pianificazione

- Un Milano–Berlino–Milano in camper entro i vincoli non è fattibile: uscire dall'Italia e rientrare costa circa 300 km per tratta e consuma le 2 eccezioni.
- Soluzioni considerate:
  - **Anello A:** camper fino a Lipsia, Berlino in treno in giornata (ICE ~1h15). Rispetta i vincoli (~1.935 km totali).
  - **Alternativa B (scelta dall'utente, in sviluppo):** Berlino in camper, allentando i vincoli con 3 giorni lunghi invece di 2:
    - Milano → Ulma ~430 km
    - Berlino → Norimberga ~440 km
    - Lindau/Ulma → Milano ~300–430 km
    - alcune tappe saranno intorno a 160–190 km (es. Lipsia → Berlino).
- Tappe e attrazioni emerse finora: Lindau, Ulma, Nördlingen, Rothenburg ob der Tauber, Bamberga, Norimberga, Pottenstein (Svizzera Francone), Saalfeld (Feengrotten), Erfurt, Lipsia (zoo), Günzburg (Legoland), Füssen (Neuschwanstein).
- Distanze Google Maps già rilevate (km): Milano–Ulma 429; Milano–Lindau 318; Lindau–Ulma 119; Ulma–Rothenburg 137; Ulma–Nördlingen ~83; Lipsia–Erfurt 147; Ulma–Milano 430; Günzburg–Milano 449.
- Da fare: completare le distanze di tutte le tappe di B, scegliere campeggi adatti a 3 camper, verificare le tappe al limite dei 150 km.

## Note pratiche

- Pedaggi/vignette: Svizzera (vignetta) se si passa dal San Bernardino/Lindau; Austria (vignetta + Brennero) se si passa dal Tirolo. Oltre 3,5 t: GO-Box in Austria, LSVA in Svizzera.
- Fine agosto: in alcuni Länder (soprattutto Baviera) ci sono ancora vacanze scolastiche → prenotare i campeggi con largo anticipo (Füssen, Legoland, Berlino).

## Calcolo distanze (ambiente cloud)

- La rete della sessione blocca di default `www.google.com`; va abilitato tra i domini consentiti nelle impostazioni dell'ambiente (Network access).
- `WebFetch` su Google Maps non restituisce i risultati; l'API Directions richiede una chiave. Funziona invece **Playwright/Chromium** (preinstallato) che apre `https://www.google.com/maps/dir/<A>/<B>` e legge testo "N km / durata / tramite …" della pagina (interfaccia in italiano).
- Salvare script e output temporanei nello scratchpad, non nel repository.
