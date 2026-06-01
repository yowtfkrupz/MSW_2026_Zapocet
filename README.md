# Seminární práce z kurzu Matematický software (Kl/MSW)
**Autor:** Tomáš Krupička
**Rok:** 2026  
**Odkaz na Jupyter Notebook:** (https://github.com/yowtfkrupz/MSW_2026_Zapocet)

## Shrnutí nejdůležitějších myšlenek a výsledků simulací

Tato seminární práce se věnuje kódové implementaci, parametrizaci a vizualizaci tří odlišných typů matematických modelů. Cílem bylo analyzovat chování modelovaných systémů v čase, interpretovat dynamické přechody a demonstrovat klíčové koncepty jako deterministický chaos, epidemiologický přenos a prostorovou samoorganizaci.

### 1. Úloha 1: Lineární a nelineární oscilátory
V první části byla provedena komparace lineárního tlumeného harmonického oscilátoru a nelineárního buzeného Duffingova oscilátoru. Oba systémy byly transformovány na soustavy dvou obyčejných diferenciálních rovnic (ODE) prvního řádu a řešeny numericky.
* **Lineární systém:** Ukázal plynulé kvantitativní změny uvnitř jednotlivých režimů (slabé, silné tlumení), avšak bod *kritického tlumení* představuje ostrou kvalitativní bifurkaci, kde se mění podstata řešení z oscilatorického na aperiodické. Byla prodiskutována problematika rezonance a možnost symbolického řešení pomocí knihovny SymPy.
* **Nelineární systém (Duffing):** Pro doporučené parametry vykazuje systém deterministický chaos s vysokou citlivostí na počáteční podmínky. Zatímco malé počáteční podmínky drží systém v periodickém režimu jedné ze dvou potenciálových jamek, velké počáteční podmínky umožňují chaotické přeskakování mezi nimi. Pomocí stroboskopického vzorkování v periodě buzení ($t = nT$) byl úspěšně vizualizován podivný atraktor vykazující fraktální strukturu.

### 2. Úloha 2: Programová implementace SIR modelu
Byl implementován deterministický kompartmentový model šíření infekcí (S-I-R) s konstantní populací ($N = 100\ 000$) a konstantní incidencí. Model byl podroben simulaci pro 5 odlišných onemocnění lišících se základním reprodukčním číslem ($R_0$) a průměrnou dobou infekčnosti.
* **Klíčové zjištění:** Hodnota $R_0$ zásadním způsobem diktuje rychlost, vrchol a rozsah epidemie. 
* U méně nakažlivých chorob (Chřipka, $R_0=1.3$) je nástup pozvolný (vrchol až 72. den), nápor na populaci nízký a polovina populace nákaze zcela unikne.
* U vysoce nakažlivých chorob (Plané neštovice $R_0=10$, Spalničky $R_0=15$) proběhne epidemie jako explozivní šoková vlna s vrcholem v prvních 7–10 dnech, která bleskově zasáhne téměř 100 % populace, čímž dojde k rychlému dosažení kolektivní imunity a totálnímu utichnutí epidemie do 90-100 dnů.

### 3. Úloha 3: Vlastní mřížkový model (Conwayova Hra života)
Jako vlastní téma byl zvolen diskrétní mřížkový celulární automat s periodickými okrajovými podmínkami pracující na základě čtyř lokálních deterministických pravidel (pravidla pro podvýživu, přelidnění, rovnováhu a reprodukci).
* **Klíčové zjištění:** Model perfektně demonstruje princip *emergence*. Z počáteční náhodné, chaotické konfigurace živých a mrtvých buněk se systém v průběhu cca 50 generací sám přetransformuje do stavu dynamické rovnováhy. Během této fáze chaotické struktury zanikají a generují se izolované, stabilní geometrické útvary (tzv. zátiší a periodické oscilátory), které již dál do prostoru neexpandují.

---

## Prohlášení o obsahu Jupyter Notebooku
V přiloženém Jupyter Notebooku (`.ipynb`) je plně obsažen:
1. **Funkční kód modelů:** Využívající knihovny `numpy` pro maticové operace a `scipy.integrate.solve_ivp` pro řešení ODE soustav.
2. **Vizualizace výsledků:** Grafy časových řad, fázových prostorů, stroboskopických řezů a prostorového vývoje mřížky.
3. **Komentáře a diskuse:** Podrobná interpretace chování systémů, včetně exaktních numerických odpovědí na všechny otázky ze zadání.
