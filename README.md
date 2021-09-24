## Boolgram
L'applicazione Boolgram replica il funzionamento di Instagram Web attraverso l'uso di Vue Cli, la suddivisione in Componenti Vue, Javascript ed SCSS.
Essa presenta un layout suddiviso in una Nav e un Main.
La componente Nav è fissata in alto e suddivisa in ulteriori tre section: una per il Logo, una per la ricerca (momentaneamente statica) e una per le informazione dell'account. 
La sezione main è suddivisa in due Componenti una Left e una Right. A seconda del valore del loader settato inizialmente a false si potrà visualizzare l'effetto Skeleton per i primi 2 secondi per poi visualizzare le Stories e i Post.
Per lo Skeleton c'è una cartella nella sezione components che contiene StorySkeleton,PostSkeleton per la parte Left e HintSkeleton per la parte Right.
La sezione Left contiene ulteriori components, Story e Post che rappresentano rispettivamente la Singola Storia e il Singolo Post. I dati visualizzati in queste componenti sono date da chiamate API asincrone ritardate di 2 secondi.
La sezione Right è invece suddivisa in tre sezioni:
la prima per le informazioni di dettaglio dell'account,
la seconda per i suggerimenti ottenuti da una chimata API ritardata di 2 secondi e la terza sezione un footer con il copyright.
Le funzionalità di questo applicativo sono la possibilità di visualizzare i commenti al di sotto del post, l'aggiunta di un nuovo commento e l'effetto grafico al click del cuore.
Gli effetti grafici sono ottenuti dall'utilizzo del Framewrok Bootstrap e dei fogli di stile in SCSS.
Tutto il progetto è stato incluso, successivamente in un container Docker inizializzato nel file devcontainer.json.
Per poter utilizzare il container ho ususfruito di un estensione di VSC Remote-Container e ho scaricato Docker for Desktop.
## Project setup
```
npm install
```
### Compiles and hot-reloads for development
```
npm run serve
```
### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```
### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
