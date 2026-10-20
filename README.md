# Porovnání blbého a chytrého výtahu
# Autoři Borovka, D. Hruška 3IT
# Spuštění
https://rudisss09.github.io/porovnani_vytahu/
stáhnout .json složku a pak vložit do stránky dle vyzvání

## Zadání

Oba výtahy byly vyzkoušeny na **stejném zadání** `zadani_porovnani_vytahu.json` s otiskem **55E5-36C8**. Budova má 8 pater (0–7), kabina pojme 7 lidí, jezdí rychlostí nejvýše 2 m/s a na jednotlivých patrech čeká celkem 100 cestujících. Jsou zastoupeny hromadné příchody v přízemí, návraty do přízemí a jízdy mezi podlažími. Výtah nezná cíle lidí, kteří ještě čekají, pouze požadovaný směr jízdy (`info.destVisible = false`).

## Jak algoritmy fungují

**Blbej výtah (původní algoritmus):** Když má kabinu prázdnou, dojede pro člověka, který čeká nejdéle. Dovolí nastoupit lidem v jednom patře a následně je rozveze podle pořadí nástupu. Cestou nepřibírá nikoho dalšího.

**Chytrej výtah (upravený algoritmus):** Při přepravě drží směr, vysazuje cestující podle nejbližšího dosažitelného cíle a po cestě může přibrat čekající jedoucí stejným směrem, je-li v kabině místo. Pro prázdnou kabinu volí vhodné nástupní patro s ohledem na vzdálenost, stáří požadavku a velikost skupiny. Algoritmus nesleduje budoucí příjezdy osob.

## Naměřené výsledky

| Metrika | Blbej výtah | Chytrej výtah |
| --- | ---: | ---: |
| Přepraveno | 100 / 100 | 100 / 100 |
| Průměrné čekání | 175.6 s | 97.8 s |
| Průměrná jízda | 24.9 s | 25.4 s |
| Průměrně celkem (příchod až výstup) | 200.5 s | 123.2 s |
| Nejdelší čekání | 550.9 s | 293.0 s |
| Nejdelší čas celkem | 573.5 s | 316.9 s |
| Hotovo v čase | 812.2 s | 661.8 s |
| Zastavení | 64 | 72 |
| Ujeto | 660 m | 321 m |
| Rozvezeno do 600 s | 76 | 91 |

## Vyhodnocení

Průměrný celkový čas cestujícího se zkrátil o **38.5 %**, průměrné čekání o **44.3 %** a ujetá vzdálenost o **51.4 %**. Všichni cestující dorazili do cíle dříve, celkové dokončení se zkrátilo o **18.5 %**. Chytrej výtah však častěji zastavuje a průměrná samotná jízda je o přibližně 0.5 s delší, protože bere lidi cestou.

**Závěr:** Pro toto konkrétní zadání je chytřejší algoritmus výrazně lepší, především zkracuje čekání a omezuje zbytečné popojíždění. Při jiném rozložení cestujících by se výsledky mohly lišit.

## Jak výsledky zopakovat

Otevři `vytah_blby.html` v prohlížeči a načti `zadani_porovnani_vytahu.json` tlačítkem **Vybrat soubor**. Poté otevři `vytah_chytry.html`, načti **stejný JSON** a porovnej údaje v části **Výsledek**. Otisk zadání musí být v obou případech **55E5-36C8**. V HTML chytřejší verze je změněný jen blok `<script id="algoritmus">`.




