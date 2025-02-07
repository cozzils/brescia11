# Documentazione Tecnica: Sito Web Scout Oratorio

## Sommario
Questa documentazione fornisce una descrizione dettagliata del sito web dell'Oratorio Scout, progettato per promuovere le serate di giochi e attività organizzate dal gruppo scout locale. Il sito è sviluppato utilizzando HTML5, CSS3 (tramite Tailwind CSS) e JavaScript, con particolare attenzione alla responsività e all'esperienza utente.

## Struttura del Progetto
La struttura del progetto è organizzata nel seguente modo:

```
scout-oratorio-website/
├── index.html          # File principale del sito
├── assets/            
│   └── images/         # Directory per le immagini (da aggiungere)
└── README.md          # Documentazione del progetto
```

## Tecnologie Utilizzate
- HTML5: Struttura semantica del documento
- CSS3 (Tailwind CSS 2.2.19): Framework per lo styling
- JavaScript: Gestione della geolocalizzazione e interattività
- Google Maps Embed API: Integrazione delle mappe

## Componenti del Sito

### 1. Navigation Bar
Posizione: Parte superiore del sito
File: index.html (linee 20-33)
Caratteristiche:
- Logo "Scout Oratorio"
- Menu di navigazione responsive
- Collegamenti a tutte le sezioni principali
- Stile: sfondo verde (bg-green-700)

### 2. Header/Hero Section
Posizione: Prima sezione dopo la navbar
File: index.html (linee 35-42)
Caratteristiche:
- Titolo principale
- Sottotitolo descrittivo
- Pulsante Call-to-Action
- Pattern di sfondo personalizzato

### 3. Sezione "Chi Siamo"
Posizione: Seconda sezione
File: index.html (linee 44-59)
Caratteristiche:
- Layout a due colonne su desktop
- Immagine rappresentativa
- Testo descrittivo
- Sfondo bianco per massima leggibilità

### 4. Sezione Attività
Posizione: Terza sezione
File: index.html (linee 61-82)
Caratteristiche:
- Grid responsive di cards
- Tre categorie di attività
- Design con ombreggiature e bordi arrotondati

### 5. Sezione Mappa
Posizione: Quarta sezione
File: index.html (linee 84-97)
Caratteristiche:
- Iframe Google Maps integrato
- Funzionalità di geolocalizzazione
- Pulsante per trovare il percorso
- Gestione degli errori

### 6. Form di Contatto
Posizione: Quinta sezione
File: index.html (linee 99-123)
Caratteristiche:
- Form validato
- Campi: Nome, Email, Messaggio
- Design responsivo
- Feedback visivo sugli input

### 7. Footer
Posizione: Parte inferiore del sito
File: index.html (linee 125-129)
Caratteristiche:
- Copyright notice
- Sfondo verde coordinato con la navbar

## Funzionalità JavaScript

### Sistema di Geolocalizzazione
File: index.html (linee 131-168)
Funzionalità principali:

1. Inizializzazione Mappa:
```javascript
function initMap() {
    const mapFrame = document.getElementById('map-frame');
    mapFrame.src = `https://www.google.com/maps/embed/v1/place?key=YOUR_API_KEY&q=${destinationCoords.lat},${destinationCoords.lng}`;
}
```

2. Gestione della Posizione Utente:
```javascript
navigator.geolocation.getCurrentPosition(
    (position) => {
        const userCoords = {
            lat: position.coords.latitude,
            lng: position.coords.longitude
        };
        // Aggiornamento mappa con il percorso
    }
);
```

## Stili CSS e Design System

### Colori Principali
- Verde Primario: bg-green-700
- Bianco: bg-white
- Grigio Chiaro: bg-gray-50
- Testo Scuro: text-gray-800
- Testo Chiaro: text-gray-600

### Typography
- Titoli Principali: text-4xl/text-6xl
- Sottotitoli: text-3xl
- Testo Corpo: text-lg
- Font Family: Sistema di default Tailwind

### Responsive Breakpoints
- Mobile: Default
- Tablet: md (768px)
- Desktop: lg (1024px)

## Configurazione e Deployment

### Requisiti di Sistema
1. Server web statico
2. API Key di Google Maps valida
3. Supporto HTTPS per la geolocalizzazione

### Istruzioni di Configurazione
1. Sostituire 'YOUR_API_KEY' con una chiave API Google Maps valida
2. Aggiornare le coordinate di destinazione:
```javascript
const destinationCoords = { 
    lat: YOUR_LATITUDE, 
    lng: YOUR_LONGITUDE 
};
```
3. Personalizzare i contenuti testuali
4. Aggiungere le immagini nella directory assets/images

### Ottimizzazioni Consigliate
1. Minificazione dei file CSS e JavaScript
2. Ottimizzazione delle immagini
3. Implementazione di caching del browser
4. Aggiunta di meta tag per SEO

## Manutenzione e Aggiornamenti

### Controlli Periodici
1. Validità dell'API Key di Google Maps
2. Funzionalità di geolocalizzazione
3. Responsività su nuovi dispositivi
4. Performance generale del sito

### Procedure di Aggiornamento
1. Backup dei file esistenti
2. Test delle modifiche in ambiente di sviluppo
3. Deployment in produzione
4. Verifica post-deployment

## Problemi Noti e Soluzioni
1. Geolocalizzazione:
   - Problema: Alcuni browser bloccano di default
   - Soluzione: Implementare fallback con input manuale dell'indirizzo

2. Responsività:
   - Problema: Layout su dispositivi molto piccoli
   - Soluzione: Utilizzare classi Tailwind specifiche per schermi xs

## Supporto e Contatti
Per assistenza tecnica o modifiche al sito, contattare:
- Email: [inserire email]
- Telefono: [inserire telefono]

## Versioning
- Versione attuale: 1.0.0
- Data ultimo aggiornamento: 07/02/2025
