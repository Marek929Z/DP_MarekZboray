# Diplomová práca
## Automatizácia spracovania ionosférických dát pomocou hlbokého učenia

Študijný program: Hospodárska informatika  
Študijný odbor: Informatika  
Školiace pracovisko: Ústav umelej inteligencie (ÚUI)  
Školiteľ: doc. Ing. Peter Butka, PhD.  
Konzultanti: Ing. Viera Krešňasková, PhD.; RNDr. Šimon Mackovjak, PhD.  
Doménoví experti: RNDr. Jaroslav Chum, Ph.D.; Mgr. Jan Rusz, Ph.D.  
Vypracoval: Bc. Marek Zboray

### Abstrakt 
Táto diplomová práca sa zaoberá automatizovaným spracovaním ionosférických dát pomocou hlbokého učenia, pričom hlavným cieľom je rekonštrukcia priebehu dopplerovského signálu počas výskytu spread‑F javov a následná detekcia týchto udalostí. Práca opisuje celý postup spracovania, od prípravy obrazových vstupov a tvorby segmentačných masiek až po implementáciu segmentačného modelu určeného na identifikáciu oblastí ovplyvnených spread‑F. Na základe predikovaných masiek sa dopĺňa narušený priebeh signálu a extrahujú sa parametre potrebné na určenie výskytu jednotlivých udalostí. Výsledky potvrdzujú, že navrhnutý prístup dokáže rekonštruovať chýbajúce signálové štruktúry a umožňuje spoľahlivú automatizovanú detekciu spread‑F javov.

### Návod na použitie
Je potrebné mať nainštalované prostredie, ktoré podporuje súbory typu .ipynb. Kedže ide o súbory typu Jupyter Notebook, jednotlive bloky predstavujú čiastkovú funkcionalitu celého kódu. Jednotlivé časti kódu (bloky) sú priamo popísané v každom súbore

### Štruktúra repozitára
Repozitár je rozdelený podľa jednotlivých etáp spracovania dát a tréningu modelov. Každý priečinok alebo notebook predstavuje samostatnú časť pipeline, ktorá bola použitá v diplomovej práci.

#### Priečinok DeepLabV3
Tento priečinok obsahuje implementáciu segmentačného modelu DeepLabV3, ktorý bol trénovaný na segmentáciu oblastí ovplyvnených spread‑F javmi.
Obsah priečinka:
- Tréningové skripty – príprava datasetu, augmentácie, definícia architektúry, tréning a validácia.
- Konfiguračné súbory – parametre modelu, nastavenia učenia.
- Výstupy modelu – ukážky predikovaných masiek, uložené checkpointy.

#### Priečinok U-net
Priečinok obsahuje implementáciu modelu U‑Net, ktorý bol použitý ako alternatívna segmentačná architektúra pre porovnanie s DeepLabV3.
Obsah priečinka:
- Tréningové notebooky – kompletný proces učenia, vizualizácie priebehu loss/accuracy.
- Modelové váhy – uložené checkpointy najlepších epoch.
- Predikcie – ukážky segmentačných masiek generovaných modelom.

#### 1_Algorithmic_mask_creation.ipynb
Prvý krok pipeline. Notebook obsahuje:
- algoritmickú tvorbu segmentačných masiek zo spektrogramov,
- detekciu štruktúr spread‑F pomocou prahovania a morfologických operácií,
- generovanie ground‑truth masiek pre trénovanie modelov.

#### 2_Algorithmic_mask_creation.ipynb
Druhá verzia algoritmickej tvorby masiek:
- vylepšené prahovanie,
- robustnejšie morfologické operácie,

#### Cropping_spectrograms.ipynb
Notebook určený na:
- načítanie pôvodných spektrogramov po jednotlivých zásielkach,
- ich orezanie na relevantné časovo‑frekvenčné oblasti.

#### Dashboard_PredictAnalysis.ipynb
Notebook slúži na:
- načítanie predikovaných masiek,
- rekonštrukciu dopplerovského priebehu signálu,
- extrakciu parametrov potrebných pre detekciu spread‑F udalostí,
- vizualizáciu výsledkov v prehľadnom dashboarde.
- 
#### README.md
Tento súbor obsahuje popis diplomovej práce, návod na použitie a štruktúru repozitára.

### Dáta
Dáta použité v diplomovej práci sú dostupné na školskom datalabe v rámci Ústavu umelej inteligencie. Nachádzajú sa v jednotlivých zásielkach na ceste: **data/lightning/MarekZboray/DP/data/RawData**

