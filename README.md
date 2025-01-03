# ![Logo](./img/readme/logo.png)

F1 Experience è un sito web dedicato agli appassionati di Formula 1, che riflette sulla storia della Formula 1, sui risultati degli ultimi Gran Premi e sulla classifica della passata stagione.

# Spiegazione del progetto

## HTML ([index](index.html))

Il file `index.html` contiene la struttura principale del sito.

Il file può essere diviso in **4 parti**:

1. **Header**:
   - Include il logo, che rimanda alla homepage.
   - Un menu di navigazione (`nav`) con link alle diverse sezioni del sito. C'è una voce "Classifica" che contiene un menù a tendina per la classifica piloti e i costruttori.

```html
  <!-- Header -->
  <header>
    <div class="logo">
    <a href="index.html"><img src="/img/logo.png" alt="F1 Experience" id="logof1"></a>
    </div>
    <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li class="dropdown"> <!-- Menù a tendina -->
            <a href="#">Classifica <i class='bx bx-chevron-down' ></i></a>
            <ul class="dropdown-menu">
              <li><a href="./pages/piloti.html">Piloti</a></li>
              <li><a href="./pages/costruttori.html">Costruttori</a></li>
            </ul>
          </li>
        </ul>
      </nav>
  </header>
```

2. **Introduzione**:

- Una sezione di introduzione con un'immagine di sfondo e un titolo che invita gli utenti a scoprire la passione e la velocità della Formula 1.

```html
  <!-- Introduzione -->
  <section class="hero">
    <div class="hero-content">
      <h2>SCOPRI LA PASSIONE, LA VELOCITÀ E L'INNOVAZIONE DEL MONDO DELLA FORMULA 1!</h2>
    </div>
  </section>
```

3. **Storia**

- Una sezione che presenta una timeline con eventi storici significativi. Ogni item della timeline è un link a una pagina esterna (Wikipedia) che fornisce maggiori dettagli sull'evento.

```html
  <!-- Storia della Formula 1 -->
  <section class="history">
    <h2>La Storia della Formula 1</h2>
    <p>Esplora la storia affascinante della Formula 1, dai primi giorni alle moderne tecnologie dei motori ibridi.</p>
    <div class="timeline">
        <div class="timeline-item">
        <a href="https://it.wikipedia.org/wiki/Formula_1#Anni_1950:_le_vetture_a_motore_anteriore" target="_blank">
        <h3>1950</h3>
        <p>Inizio della Formula 1 come campionato mondiale ufficiale.</p>
        </a>
      </div>
      <!-- Continuo con il resto della storia -->
    </div>
  </section>
```

4. **Gran Premi**

- Presenta dei riquadri interattivi che mostrano i Gran Premi recenti. Ogni card è un link che rimanda ai dettagli del Gran Premio sul sito ufficiale della Formula 1.

```html
<!-- Gran Premi -->
<section class="grid">
  <div class="card">
    <a href="https://www.formula1.com/en/racing/2024/italy.html" target="_blank">
      <img src="img/monza.avif" alt="Monza Circuit">
      <h2>MONZA GRAND PRIX</h2>
    </a>
  </div>
  <!-- Altre riquadri per i Gran Premi -->
</section>
```

## HTML ([piloti](./pages/piloti.html)/[costruttori](./pages/costruttori.html) )

I file `piloti.html`  e `costruttori.html `sono molto simili tra loro.

La struttura dell'*header* è identica a quella di `index.html`, ma al posto della sezione introduttiva (hero)
si trova una tabella.

```html
<!-- Tabella -->
    <section class="hero">
        <div class="table-container">
            <h1>CLASSIFICA COSTRUTTORI</h1>
            <table class="f1-table">
                <thead>
                    <tr>
                        <th>Posizione</th>
                        <th>Team</th>
                        <th>Punti</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>1</td>
                        <td>McLaren</td>
                        <td>666</td>
                    </tr>
                    <tr>
                        <td>2</td>
                        <td>Ferrari</td>
                        <td>652</td>
                    </tr>
                    <tr>
                    <!-- Resto della classifica -->
                    </tr>
                </tbody>
            </table>
        </div>
    </section>
```

## CSS

Il file `style.css` contiene l'estetica della pagina `index.html`.
`piloti.css` e `costruttori.css` sono molto simili a quest'ultimo.

Il font utilizzato si trova nella cartella [fonts](./fonts)

```css
/* Import manuale del font */
@font-face { 
    font-family: 'F1';
    src: url('../fonts/Formula1-Bold.otf') format('opentype');
    font-weight: normal;
    font-style: normal;
}
```
Il sistema del menù a tendina è fatto totalmente in CSS

```css
/* Menù a tendina */
.dropdown-menu {
  display: none; /* Nascosto all'inizio */
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #111;
  padding: 10px 0;
  list-style: none;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
  border-radius: 8px;
  transform: translateY(-10px);
  transition: opacity 0.3s ease, transform 0.3s ease;
  width: max-content;
}

.dropdown-menu li {
  padding: 0;
}

.dropdown-menu li a {
  color: #fff;
  padding: 10px 15px;
  display: block;
  text-transform: none; 
  transition: background-color 0.3s ease; 
  border-radius: 4px;
}

.dropdown-menu li a:hover {
  background-color: #333;
}

/* Mostra il menù a tendina quando il mouse è sopra il link */
.dropdown:hover .dropdown-menu {
  display: block;
  opacity: 1;
  transform: translateY(0);
}
```

I riquadri della parte finale della pagina come quelli della storia sono molto simili

```css
/* Riquadro della storia */
.timeline {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

/* Stile del riquadro */
.timeline-item {
  background-color: #f1f1f1;
  padding: 20px;
  border-radius: 10px;
  width: 250px;
  margin-bottom: 30px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

/* Ingrandendo il riquadro quando il mouse ci passa sopra  */
.timeline-item:hover {
  transform: scale(1.1); /* Il riquadro diventa il 10% più grande */
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2); /* Aggiunge un effetto sfumato */
}
  
.timeline-item h3 {
  font-size: 1.8em;
  margin-bottom: 10px;
}
  
.timeline-item p {
  font-size: 1em;
}
```

A fine della pagina c'è il footer

```css
/* Footer */
footer {
  background-color: #111;
  color: #fff;
  text-align: center;
  position: relative;
  padding: 20px;
  width: 100%;
  bottom: 0;
}
```

I file delle classifiche si distinguono solo per la loro sezione sulla tabella

```css
/* Sezione generale della Tabella */
.hero {
  padding: 40px 0;
  text-align: center;
}
  
/* Contenitore della tabella */
.table-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  overflow-x: auto;
}
  
/* Tabella */
.f1-table {
  width: 100%;
  border-collapse: collapse;
  border: 2px solid #444;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  background-color: #FFFFFF;
  border-radius: 12px; /* Bordo tondeggiante */
  overflow: hidden; /* Rimuove il bordo all'interno */
    
}
  
.f1-table th, .f1-table td {
  padding: 12px 15px;
  text-align: center;
  font-size: 1.1rem;
    
}
  
/* Stile per le intestazioni */
.f1-table th {
  background-color: #111;
  color: #fff;
  font-size: 1.2rem;
  text-transform: uppercase;
  font-weight: bold;
}
  
/* Colori per le righe */
.f1-table tr:nth-child(even) {
  background-color: #F3F3F3;
}
  
.f1-table tr:hover {
  background-color: #8d8d8d;
}
```

# Conclusione

Queste erano soltanto le informazioni principali, consiglio di controllare il codice sorgente per vedere tutte
le informazioni 