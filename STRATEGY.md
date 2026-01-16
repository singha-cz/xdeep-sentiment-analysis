# Analýza sentimentu textu pomocí hlubokých neuronových sítí

## 1. Analýza problému

Cílem tohoto projektu je vytvořit model pro automatickou analýzu sentimentu textu, tedy úlohu klasifikace textových vstupů podle jejich emocionálního zabarvení. Konkrétně se jedná o rozlišení mezi pozitivním a negativním sentimentem.

Analýza sentimentu nachází uplatnění v celé řadě oblastí, jako je hodnocení zákaznických recenzí, analýza reakcí na sociálních sítích, monitoring veřejného mínění nebo doporučovací systémy. Problém je zajímavý zejména tím, že význam textu není dán pouze jednotlivými slovy, ale také jejich kontextem, slovosledem a často i implicitním významem.

Projekt je zaměřen na praktické pochopení principů hlubokého učení v oblasti zpracování přirozeného jazyka (NLP).

---

## 2. Analýza dat

Pro trénování a vyhodnocení modelu je použit veřejně dostupný dataset **Sentiment140**, který obsahuje krátké textové příspěvky ze sociální sítě X (Twitter).

Každý záznam v datasetu obsahuje:

- text tweetu,
- anotaci sentimentu (pozitivní / negativní),
- další metadata (např. ID, čas vytvoření).

Dataset je označený (labeled), což znamená, že ke každému textu je znám správný výstupní štítek. To umožňuje použití řízeného učení (supervised learning).

<!-- Původně bylo zvažováno vytvoření vlastního datasetu pomocí web scrapingu recenzí z portálu ČSFD.cz. Tento přístup byl však opuštěn z důvodu technických omezení (blokování většího počtu požadavků serverem – HTTP chyba „Too many requests“) a také s ohledem na etické a právní aspekty automatizovaného stahování obsahu. -->

---

## 3. Návrh řešení

Navržené řešení využívá hlubokou neuronovou síť pro zpracování textu. Textové vstupy jsou nejprve převedeny na číselnou reprezentaci pomocí tokenizace a embedding vrstvy.

Architektura modelu zahrnuje:

- vstupní vrstvu pro sekvence tokenů,
- embedding vrstvu pro reprezentaci slov,
- rekurentní neuronovou síť (LSTM),
- plně propojenou (Dense) výstupní vrstvu s binární klasifikací.

Model je navržen tak, aby zachycoval kontext slov v textu a byl schopen rozlišit sentiment i u krátkých a neformálních textů, typických pro sociální sítě.
