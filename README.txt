VAULT — PWA per la gestione delle password
===========================================

CONTENUTO
- index.html: interfaccia e logica dell'app
- manifest.json: configurazione installazione PWA
- sw.js: cache offline
- icone PNG per la schermata iniziale Android

FUNZIONI
- Campi: SITO, Nome Utente, Password, Note
- Ricerca istantanea per nome del sito
- Creazione, modifica e visualizzazione delle credenziali
- Copia di nome utente e password negli appunti
- Archivio cifrato con AES-GCM a 256 bit e chiave derivata via PBKDF2
- Esportazione/importazione di backup cifrato
- Interfaccia responsive, tema scuro e funzionamento offline dopo il primo caricamento

INSTALLAZIONE SU ANDROID
1. Pubblicare tutti i file su un hosting HTTPS (ad esempio un sito statico personale).
   Per installazione PWA e service worker è necessario HTTPS; localhost è ammesso solo
   per sviluppo. Non aprire index.html direttamente dal file manager.
2. Aprire l'indirizzo HTTPS con Chrome su Android.
3. Dal menu ⋮ scegliere “Installa app” oppure “Aggiungi a schermata Home”.
4. Avviare Vault dall'icona e creare una password principale robusta.
5. Eseguire periodicamente “Backup” e conservare il file JSON cifrato in un luogo sicuro.

NOTE IMPORTANTI DI SICUREZZA
- L'archivio è cifrato nel browser sul dispositivo; non viene inviato a un server dall'app.
- La password principale non viene salvata. Se viene dimenticata, i dati non sono recuperabili.
- I dati sono legati al browser/profilo e al dispositivo: cancellare i dati del sito o disinstallare
  il browser può eliminare l'archivio. Conservare un backup cifrato.
- Usare un dispositivo aggiornato, un blocco schermo sicuro e non condividere la password principale.
- La funzione copia trasferisce la password negli appunti, che potrebbero essere accessibili ad altre app.
- Questa è una soluzione personale di base, non un prodotto sottoposto ad audit di sicurezza.
- Prima di usarla per credenziali particolarmente critiche, valutare un password manager consolidato
  e sottoposto a revisione indipendente.

PERSONALIZZAZIONE
Per aggiornare la PWA dopo modifiche, incrementare il nome CACHE in sw.js (es. vault-pwa-v2).
