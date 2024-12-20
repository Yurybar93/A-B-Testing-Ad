# A/B-Testing Analyse

## Projektübersicht
Dieses Projekt analysiert die Daten eines A/B-Tests, um die Leistung von zwei Werbebietmodellen zu bewerten: **Maximum Bidding** (Kontrollgruppe) und **Average Bidding** (Testgruppe). Ziel der Analyse ist es, festzustellen, ob das neue Gebotsmodell das bestehende Modell in Bezug auf wichtige Metriken wie CTR, CPC, CPM, CVR und CPA übertrifft.

## Datensatz
Der Datensatz enthält Daten für zwei Gruppen (Kontrolle und Test) mit den folgenden Spalten:
- **Campaign Name**: Name der Kampagne (Kontrolle oder Test).
- **Date**: Datum der Datenerfassung.
- **Spend [USD]**: Ausgaben in USD.
- **# of Impressions**: Gesamtanzahl der Anzeigenimpressionen.
- **Reach**: Erreichte eindeutige Benutzer.
- **# of Website Clicks**: Insgesamt generierte Website-Klicks.
- **# of Searches**: Anzahl der initiierten Suchanfragen.
- **# of View Content**: Anzahl der Benutzer, die Inhalte angesehen haben.
- **# of Add to Cart**: Anzahl der zum Warenkorb hinzugefügten Produkte.
- **# of Purchase**: Anzahl der getätigten Käufe.

## Wichtige Metriken
Die folgenden Metriken werden berechnet und analysiert:
- **CTR (Click-Through Rate)**: \( \text{CTR} = \frac{\text{# of Website Clicks}}{\text{# of Impressions}} \times 100 \)
- **CPC (Cost per Click)**: \( \text{CPC} = \frac{\text{Spend [USD]}}{\text{# of Website Clicks}} \)
- **CPM (Cost per Mille)**: \( \text{CPM} = \frac{\text{Spend [USD]}}{\text{# of Impressions}} \times 1000 \)
- **CVR (Conversion Rate)**: \( \text{CVR} = \frac{\text{# of Purchase}}{\text{# of Website Clicks}} \times 100 \)
- **CPA (Cost per Acquisition)**: \( \text{CPA} = \frac{\text{Spend [USD]}}{\text{# of Purchase}} \)

## Statistische Analyse
Das Projekt umfasst folgende statistische Analysen:

1. **Datenverteilungsanalyse**:
   - Diagramme der Datenverteilung (Q-Q-Diagramme, Histogramme), um die Normalverteilung zu bewerten.

2. **T-Tests**:
   - Unabhängige Stichproben-\( t \)-Tests werden durchgeführt, um die Mittelwertunterschiede zwischen der Kontroll- und Testgruppe für jede Metrik zu vergleichen.
   - Signifikanzniveau: \( \alpha = 0.05 \).

3. **Konfidenzintervalle**:
   - Konfidenzintervalle für sowohl Verhältnis- als auch kontinuierliche Metriken werden berechnet, um den Bereich der Unterschiede zwischen den Gruppen zu verstehen.

### Visualisierungen
n- Balkendiagramme zum Vergleich aggregierter Metriken.
- Q-Q-Diagramme zur Prüfung der Daten-Normalität.

## Ergebnisse
| Metrik               | Teststatistik | P-Wert    | Schlussfolgerung                  |
|----------------------|---------------|-----------|------------------------------------|
| Spend [USD]         | -2.793        | 0.007     | Statistisch signifikant           |
| # of Impressions    | 4.885         | 0.000009  | Statistisch signifikant           |
| Reach               | 5.300         | 0.000002  | Statistisch signifikant           |
| # of Website Clicks | -1.577        | 0.120     | Nicht signifikant                 |
| # of Searches       | -1.137        | 0.260     | Nicht signifikant                 |
| # of View Content   | 0.476         | 0.636     | Nicht signifikant                 |
| # of Add to Cart    | 4.249         | 0.000080  | Statistisch signifikant           |
| # of Purchase       | 0.030         | 0.976     | Nicht signifikant                 |
| CTR                 | -3.922        | 0.000238  | Statistisch signifikant           |
| CPC                 | 0.501         | 0.618     | Nicht signifikant                 |
| CPM                 | -4.663        | 0.000019  | Statistisch signifikant           |
| CVR                 | 1.500         | 0.139     | Nicht signifikant                 |
| CPA                 | -1.307        | 0.196     | Nicht signifikant                 |

## Fazit
- Das neue Gebotsmodell zeigte bei einigen Metriken (z. B. Impressions, CTR) signifikante Verbesserungen, jedoch nicht bei anderen (z. B. Website Clicks).
- Empfehlungen zur Einführung des Average Bidding-Modells sollten basierend auf geschäftlichen Prioritäten und weiteren Tests gegeben werden.

## Anforderungen
Das Projekt erfordert die folgenden Python-Bibliotheken:
- pandas
- numpy
- matplotlib
- seaborn
- scipy