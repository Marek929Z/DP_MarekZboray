# Diplomová práca
## Automatizácia spracovania ionosférických dát pomocou hlbokého učenia

Študijný program: Hospodárska informatika
Študijný odbor: Informatika
Školiace pracovisko: Ústav umelej inteligencie (ÚUI)
Školiteľ: doc. Ing. Peter Butka, PhD.
Konzultanti: Ing. Viera Krešňasková, PhD.; RNDr. Šimon Mackovjak, PhD.
Vypracoval: Bc. Marek Zboray

### Popis práce
Táto diplomová práca sa zaoberá automatizovaným spracovaním ionosférických dát pomocou hlbokého učenia, pričom hlavným cieľom je rekonštrukcia priebehu dopplerovského signálu počas výskytu spread-F javov a následná detekcia týchto udalostí. Práca opisuje celý postup spracovania, od prípravy obrazových vstupov a tvorby segmentačných masiek až po implementáciu segmentačného modelu určeného na identifikáciu oblastí ovplyvnených spread-F. Na základe predikovaných masiek sa dopĺňa narušený priebeh signálu a extrahujú sa parametre potrebné na určenie výskytu jednotlivých udalostí. Výsledky potvrdzujú, že navrhnutý prístup dokáže rekonštruovať chýbajúce signálové štruktúry a umožňuje spoľahlivú automatizovanú detekciu spread-F javov.


### Dáta
Dáta použité v diplomovej práci sú dostupné na školskom datalabe v rámci Ústavu umelej inteligencie. Nachádzajú sa v jednotlivých zásielkach na ceste: data/lightning/MarekZboray/DP/data/RawData

