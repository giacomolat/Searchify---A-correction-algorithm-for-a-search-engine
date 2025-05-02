![image](https://github.com/user-attachments/assets/1b701899-f179-4f08-a4cf-d50720bc827b)
# Master Executive in AI Development - ProfessionAI
# Searchify - Algoritmo di Correzione per il Motore di Ricerca 

## 📌 Descrizione del Progetto
Searchify è una startup che offre un motore di ricerca interno per aziende di medie dimensioni. L’esperienza utente è spesso compromessa da errori di digitazione nelle query di ricerca, che portano a risultati nulli o irrilevanti. Questo progetto implementa un **algoritmo di correzione automatica** basato sulla distanza di Levenshtein per suggerire la parola corretta più probabile a partire da un dizionario predefinito.

## 🎯 Obiettivo
* Rilevare automaticamente errori ortografici nelle query di ricerca.
* Suggerire correzioni plausibili.
* Restituire risultati pertinenti anche in presenza di errori.

## ⚙️ Funzionalità
* Calcolo della **distanza di Levenshtein** tra la parola inserita e quelle nel dizionario.
* Normalizzazione dei dati per un confronto case-insensitive.
* Restituzione della parola corretta più simile, o della stessa parola se già valida.
* Gestione di errori realistici: lettere invertite, doppie, omissioni e inserimenti.

## 🧠 Architettura del Codice
### Funzioni principali
* `levenshtein_distance(s, t)`:  
  Calcola il numero minimo di operazioni (inserimento, cancellazione, sostituzione) necessarie per trasformare la stringa `s` nella stringa `t`.
* `suggest_correction(query, dictionary)`:  
  Verifica se `query` è già presente nel dizionario; in caso contrario confronta `query` con ogni parola del dizionario tramite distanza di Levenshtein e restituisce la parola con distanza minima.

## 🧪 Test
Il programma è stato validato con un dizionario di almeno 50 parole e due serie di test:

* ✅ Parole corrette
  * rapporto → rapporto
  * vendite → vendite
  * server → server
  * azienda → azienda
  * backup → backup

* ❌ Parole errate
  * raporto → rapporto
  * venditte → vendite
  * docummento → documento
  * serber → server
  * aziensa → azienda
  * backu → backup
  * databaes → database
  * pefffomanse → performance

Esempio di output:

`Input: raporto => Suggerimento: rapporto`

`Input: venditte => Suggerimento: vendite`

`Input: docummento => Suggerimento: documento`

In aggiunta, è stato testato il comportamento case-insensitive con un dizionario in MAIUSCOLO e query in maiuscolo, minuscolo o misto.

## 📂 Dizionario 
Di seguito un estratto delle oltre 50 parole aziendali utilizzate:

"rapporto", "vendite", "2023", "documento", "progetto", "analisi",
"fatturato", "budget", "strategia", "marketing", "risultati",
"cliente", "servizio", "prodotto", "offerta", "contratto",
"fattura", "fornitore", "ordine", "spedizione", "pagamento",
"database", "report", "statistiche", "performance", "obiettivo",
"riunione", "agenda", "resoconto", "bilancio", "risorse",
"umane", "formazione", "tecnologia", "sicurezza", "accesso",
"autenticazione", "profilo", "utente", "account", "password",
"backup", "sistema", "rete", "server", "cloud", "innovazione",
"gestione", "processo", "azienda"

## 💻 Esecuzione
1. Clona il repository:
`git clone https://github.com/tuo-username/searchify-spellchecker.git
cd searchify-spellchecker`
2. Assicurati di avere Python 3 installato.
3. python spellchecker.py

## 📜 Licenza
Questo progetto è rilasciato con licenza GNU GPL v3.
Vedi il file LICENSE per i dettagli.
