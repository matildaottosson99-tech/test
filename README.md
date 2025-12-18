Projektuppgift: Automatiserad data-pipeline 🚀
Kurs: Data Science | Grupp: [Namn på gruppmedlemmar]

Detta projekt bygger en automatiserad datapipeline som hämtar dagliga transaktioner, normaliserar datan och lagrar den i en SQLite-databas. Datan visualiseras sedan i en Jupyter Notebook.

Projektstruktur
Vi använder uv för att hantera projektet och dess beroenden.

dags/transaction_dag.py - Airflow DAG som sköter hämtning och lagring.

koksgledje.db - SQLite-databasen (normaliserad).

analysis.ipynb - Jupyter Notebook med visualiseringar.

pyproject.toml - Projektdefinition och beroenden.

Pipeline-flöde
Extract: Hämtar transaktioner (CSV) från schizoakustik.se med requests.

Transform: - Konverterar datum till standardformat.

Filtrerar ut data som redan finns i databasen (baserat på TransactionDate).

Normaliserar datan till två tabeller: Transactions och TransactionDetails.

Load: Sparar ny data till koksgledje.db.

Visualize: Jupyter Notebook läser från databasen och genererar grafer.

Installation & Körning
För att köra detta projekt lokalt:

Installera beroenden:

Bash
uv sync
Starta Airflow: (Beskriv här hur ni kör Airflow, t.ex. standalone eller via Docker).

Databasmodell
Datan är normaliserad i följande tabeller:

Transactions: TransactionID (PK), TransactionDate, CustomerID.

TransactionDetails: TransactionID (FK), ProductID, Quantity, Price.
