# TheaterKulturReviews-Trello2HTML

Meine Theater & Kultur Reviews aus Trello in schönes HTML (und optional CSV) exportieren.

Das Jupyter Notebook [`Trello2HTML.ipynb`](Trello2HTML.ipynb) liest Karten von einem
Trello-Board (inkl. Titelbild und den Custom Fields "Datum" und "Sterne") und erzeugt daraus
eine hübsch formatierte HTML-Übersicht mit eingebetteten Bildern, gruppiert nach Liste und Jahr.

## Voraussetzungen

- Python 3
- Ein Trello API Key + Token (kostenlos unter https://trello.com/power-ups/admin)
- Die Board-ID des Trello-Boards, das exportiert werden soll

```bash
pip install -r requirements.txt
```

## Zugangsdaten

**Wichtig: Trello API Key und Token gehören niemals in den Code oder ins Repo**, auch nicht in
ein privates. Das Notebook liest sie stattdessen aus Umgebungsvariablen — sind sie nicht gesetzt,
fragt es beim Ausführen interaktiv danach:

```bash
export TRELLO_API_KEY="..."
export TRELLO_TOKEN="..."
export TRELLO_BOARD_ID="..."
```

Alternativ können diese drei Werte in einer lokalen `.env`-Datei stehen (wird per `.gitignore`
nicht mit eingecheckt).

## Verwendung

Notebook öffnen (lokal mit Jupyter oder in Google Colab) und der Reihe nach ausführen. Am Ende
entstehen:

- eine HTML-Datei mit allen Reviews (Bilder eingebettet als Base64, direkt teilbar/druckbar)
- optional eine CSV-Datei, wenn `YEAR = ""` (alle Jahre) gesetzt ist

Die Custom-Field-IDs (`DATE_FIELD_ID`, `STARS_FIELD_ID`) sowie die Sterne-Mapping-Tabelle im
Notebook müssen einmalig an das eigene Trello-Board angepasst werden.
