# Firebase per Idee Geniali — Guida passo passo

Con Firebase tutti vedono **le stesse idee** su PC, telefono e da tutto il mondo.

## 1. Crea il progetto Firebase (gratis)

1. Vai su [https://console.firebase.google.com](https://console.firebase.google.com)
2. Accedi con Google (stesso account se vuoi)
3. **Aggiungi progetto** → Nome: `IdeeGeniali` (o come preferisci)
4. Disattiva Google Analytics se non ti serve → **Crea progetto**

## 2. Crea il database Firestore

1. Menu sinistro → **Build** → **Firestore Database**
2. **Crea database** → Modalità **Produzione** (poi mettiamo le regole)
3. Posizione: `europe-west1` (o la più vicina all’Italia)
4. **Abilita**

## 3. Regole di sicurezza

1. Scheda **Regole** in Firestore
2. Sostituisci tutto con il contenuto del file `firestore.rules` di questo progetto
3. **Pubblica**

## 4. Registra l’app Web

1. Impostazioni progetto (icona ingranaggio) → **Le tue app**
2. Icona **Web** `</>`
3. Nickname: `Idee Geniali Web`
4. **Registra app**
5. Copia l’oggetto `firebaseConfig` che ti mostra

## 5. Incolla la config nel progetto

Apri `firebase-config.js` e sostituisci **tutti** i valori `INSERISCI_...` con quelli reali. Esempio:

```javascript
window.firebaseConfig = {
    apiKey: "AIza...",
    authDomain: "ideegeniali-xxxxx.firebaseapp.com",
    projectId: "ideegeniali-xxxxx",
    storageBucket: "ideegeniali-xxxxx.appspot.com",
    messagingSenderId: "123456789012",
    appId: "1:123456789012:web:abcdef"
};
```

## 6. Carica su GitHub

Carica **tutti** questi file nel repo `freddy197/IdeeGeniali`:

- `index.html`
- `firebase-config.js` (con config vera)
- `fabio-accardo.png`
- `firestore.rules` (opzionale, per documentazione)
- `FIREBASE-SETUP.md`

**Non** caricare chiavi segrete altre: solo `firebase-config.js` (le API key Firebase per siti web sono pubbliche per design).

## 7. GitHub Pages

1. Repo → **Settings** → **Pages**
2. Source: branch `main`, cartella `/ (root)`
3. Salva → sito: `https://freddy197.github.io/IdeeGeniali/`

## 8. Verifica

1. Apri il sito da **PC** e pubblica un’idea
2. Apri da **telefono** (altro browser) → devi vedere la stessa idea
3. In alto compare: **Cloud attivo — tutti vedono la stessa bacheca**

## Migrazione idee vecchie (solo sul tuo PC)

La prima volta che colleghi Firebase, se avevi idee solo in locale sul browser, l’app le **copia automaticamente** nel cloud (se il database è vuoto).

## Problemi comuni

| Problema | Soluzione |
|--------|-----------|
| Badge «Configura Firebase» | Compila `firebase-config.js` |
| Errore permessi | Pubblica `firestore.rules` |
| Non vedo idee altrui | Controlla che entrambi usino lo stesso URL GitHub Pages |

---

Creato per **Fabio Accardo** · Idee Geniali · Freddy (IA)
