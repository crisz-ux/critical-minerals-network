# La rete del commercio dei minerali critici

**La rete del commercio dei minerali critici: struttura, vulnerabilità e prevedibilità lungo la filiera (1995–2024)**
*The international trade network of critical minerals: structure, vulnerability and predictability along the supply chain (1995–2024)*

Cristian Sirigu, Corso di Laurea Magistrale in Data Science, Business Analytics e Innovazione, Università degli Studi di Cagliari, a.a. 2025/2026.

La tesi tratta il commercio internazionale dei minerali critici come una rete di relazioni fra paesi. La rete è divisa in quattro stadi della filiera: estrazione, raffinazione, manifattura e riciclo. Sul periodo 1995–2024 la tesi ne studia la struttura, la vulnerabilità e la prevedibilità.

## Contenuto

| File | Contenuto |
|---|---|
| `Critical_Resources_Notebook.ipynb` | Costruzione della base dati su BACI HS1992: famiglie di codici coerenti nel tempo, dizionario delle risorse, legami attivi. Poi analisi descrittiva, struttura della rete, vulnerabilità, durata delle relazioni, modello gravitazionale, restrizioni all'esportazione, modelli predittivi e scenario al 2035 |
| `02_segmento_tecnologico_HS07.ipynb` | Segmento tecnologico (semiconduttori, accumulatori, fotovoltaico) sulla release HS2007 di BACI: concentrazione dell'approvvigionamento europeo |
| `requirements.txt` | Librerie Python necessarie |
| `dati/` | File di partenza che non si scaricano o che vanno usati nell'edizione della tesi |

I notebook contengono soltanto le celle che servono a ottenere le tabelle, le figure e i numeri della tesi. La prima cella di ciascuno riporta la corrispondenza fra le tabelle o figure della tesi e le celle che le producono. I file delle immagini hanno lo stesso numero usato nella tesi. Il notebook principale è pubblicato con gli output di un'esecuzione completa, così che i risultati si possano consultare senza rieseguirlo. Il secondo va eseguito dopo il principale, perché usa i dati BACI HS2007 scaricati da questo.

## Dati di partenza

I dati si scaricano liberamente dalle fonti originali: lo fa in automatico la cella **0. Download dei dati** del notebook, che salta i file già presenti. Alcuni file sono invece inclusi nel repository, in `dati/`: l’estrazione dall’inventario OCSE, che non si scarica, e i file usati nell’edizione della tesi, perché le fonti pubblicano versioni aggiornate. Vanno messi in una cartella `dati/` accanto al notebook: il notebook la trova da solo, senza modifiche al codice. Cerca anche in `../dati`, `~/dati`, `~/Downloads/dati` e `~/Downloads`; un percorso diverso si indica con la variabile d'ambiente `TESI_DATA_DIR`.

| Fonte | Versione | Percorso dentro `dati/` |
|---|---|---|
| CEPII, BACI: commercio bilaterale per prodotto | release V202601, revisioni HS92, HS96, HS02, HS07, HS12, HS17, HS22 | `BACI/BACI_HSxx_V202601/` |
| Tavole di corrispondenza fra revisioni del Sistema Armonizzato (WCO) | da HS1996→HS1992 a HS2022→HS2017 | `CONCORDANCE/` |
| UNCTAD, SDG Pulse 2025: elenco HS dei minerali critici | 2025 | `SdgPulse2025_CM_HS_All_revisions.xlsx` (incluso) |
| CEPII, Gravity | V202211 | `Gravity_csv_V202211/` |
| Bailey, Strezhnev e Voeten: punti ideali dai voti all'Assemblea generale ONU | giugno 2024 | `IdealpointestimatesAll_Jun2024.csv`, `AgreementScores.csv.gz` (inclusi; il secondo ridotto alle colonne usate) |
| OCSE, Inventory of Export Restrictions on Industrial Raw Materials (estrazione usata nella tesi, ridotta e inclusa nel repository) | 2009–2023 | `restrizioniOECD.csv.gz` (incluso) |
| World Mining Data | 2025 | `6.4. Production_of_Mineral_Raw_Materials_of_individual_Countries_by_Minerals.xlsx` (incluso) |

## Esecuzione

Serve Python 3.12 (vanno bene anche 3.10 e 3.11). Con pandas 3 o con Python più recenti alcune operazioni non funzionano o cambiano comportamento.

```bash
pip install -r requirements.txt
jupyter notebook
```

Eseguire `Critical_Resources_Notebook.ipynb` dall'inizio alla fine, in un unico kernel. I risultati intermedi finiscono in `dati/OUT_BINARIO_A/` e le tabelle e le figure in `dati/OUT_BINARIO_A/figure/`. Poi eseguire `02_segmento_tecnologico_HS07.ipynb`, che scrive in `dati/OUT_BINARIO_C/`.

Il primo avvio scarica i file BACI, circa 60 GB una volta estratti. L'esecuzione completa richiede alcune ore e una memoria adeguata.

## Citazione

Sirigu, C. (2026). *La rete del commercio dei minerali critici: struttura, vulnerabilità e prevedibilità lungo la filiera (1995–2024)*. Tesi di laurea magistrale, Università degli Studi di Cagliari.
