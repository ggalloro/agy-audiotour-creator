# Specifica Funzionale: Creatore di Tour Audio per Milano

## 1. Introduzione
Questo documento delinea i requisiti funzionali per l'applicazione "Creatore di Tour Audio per Milano". Il suo scopo è fornire una chiara comprensione delle funzionalità principali, che permettono ai turisti e ai partecipanti agli eventi a Milano di creare audioguide personalizzate generate dall'IA per la loro visita. **NOTA IMPORTANTE:** Tutta l'interfaccia utente (UI) dell'applicazione e l'audio generato devono essere rigorosamente in lingua italiana.

## 2. Obiettivo Globale
L'obiettivo principale dell'applicazione è consentire agli utenti di inserire un elenco di monumenti, quartieri o eventi a Milano che intendono visitare, e generare automaticamente un'audioguida coesa e coinvolgente che copra quegli specifici punti di interesse, completamente in lingua italiana.

## 3. Ruoli Utente
**Visitatore di Milano / Partecipante all'Evento**
Un utente in viaggio a Milano (es. per la Design Week o un fine settimana) che desidera una guida vocale personalizzata in italiano su luoghi specifici, senza dover leggere pesanti guide cartacee.

## 4. Funzionalità Chiave

### 4.1 Gestione dell'Itinerario
*   **Aggiungi Punto di Interesse (POI):** Gli utenti devono poter inserire il nome di un luogo di Milano (es. "Duomo di Milano", "Fondazione Prada", "Navigli") tramite l'Interfaccia Utente (UI).
*   **Visualizza/Gestisci Itinerario:** Gli utenti devono poter visualizzare l'elenco attuale dei POI aggiunti.
*   **Rimuovi POI:** Gli utenti devono poter rimuovere una località dal proprio elenco.

### 4.2 Generazione del Tour Audio
*   **Avvio della Generazione:** Gli utenti devono poter avviare la generazione di una nuova audioguida dai POI selezionati tramite un'azione dedicata nell'UI (es. un pulsante "Crea il Mio Tour").
*   **Generazione dei Contenuti e Riepilogo:** L'applicazione invierà l'elenco dei POI ad un LLM. L'LLM agirà come una guida turistica milanese esperta, generando un copione riassuntivo, coinvolgente e ricco di cultura che passi in modo fluido tra i luoghi selezionati, **scritto interamente in italiano**.
*   **Sintesi Vocale:** Il copione del tour generato verrà convertito in un discorso dal suono naturale utilizzando un servizio di sintesi vocale (utilizzando voci italiane il più possibile simili a quelle di un essere umano).
*   **Compilazione Audio:** Il discorso sintetizzato verrà compilato in un singolo file audio, completo di una calorosa introduzione e di una conclusione utile, sempre in italiano.

### 4.3 Riproduzione e Download
*   **Elenco dei Tour:** Gli utenti devono poter visualizzare un elenco dei loro tour audio generati in precedenza, inclusa la data di creazione.
*   **Riproduzione:** Gli utenti devono poter ascoltare i tour audio generati direttamente dall'interfaccia dell'applicazione.
*   **Download:** Gli utenti devono poter scaricare il file audio generato sul proprio dispositivo per ascoltarlo offline mentre passeggiano per Milano.

## 5. Considerazioni Non Funzionali
*   **Estetica:** L'interfaccia utente deve avere un design elegante e premium, in linea con la capitale della moda e del design. Tutta la testualità dell'app deve essere in italiano.
*   **Reattività:** L'applicazione deve fornire chiari stati di caricamento durante il processo di generazione, poiché le conversioni LLM e TTS richiedono tempo.

## 6. Considerazioni sull'Archiviazione dei Dati
*   **POI:** L'applicazione memorizzerà l'itinerario fornito dall'utente solo per la sessione corrente (es. in memoria o in un file JSON locale temporaneo).
*   **File Audio Generati:** I file audio generati saranno memorizzati localmente sul server (es. nella directory `public/tours`) per il download e la riproduzione immediata.
