# Zadanie 1

V tomto zadaní vytvoríte základ vášho vlastného simulátora založeného na ROS2. Pri jeho riešení využijete koncepty, ktoré ste sa naučili na doterajších cvičeniach.  Úspešné splnenie všetkých požiadaviek vám zaručí 5 bodov. Riešiť ho môžete do **21.10.2021** kedy ho budete obhajovať a demonštrovať jeho funkčnosť. Zdrojové kódy musia byť odovzdané vo vašom repozitári. Na riešenie úloh môžete použiť akýkoľvek programovací jazyk, avšak ROS2 samotný disponuje knižnicami len pre **Python** a **C++**. 



## Váš simulátor bude mať tieto časti:

**Grafické prostredie (2b)** : Vytvoríte prostredie, ktoré bude zobrazovať mriežku (grid), zodpovedajúcu mape simulovaného prostredia. Na túto mriežku pridajte aj objekt simulovaného robota (akákoľvek grafická reprezentácia).

**Súbor s mapou (1b)** : Vytvorte vhodnú štruktúru pre reprezentovanie dvojrozmernej mriežkovej mapy. Hodnoty buniek v mape budú dve, teda 0 pre voľnú bunku, 1 pre obsadenú. Súbor musí byť buď vo formáte json, alebo csv.

**ROS2 uzly (1b)** : Vytvorte uzly, ktoré budú súbor s mapou čítať a zasielať dáta simulátoru tak, aby ho mohlo grafické prostredie zobraziť. Rovnako vytvorte uzly dovoľujúce úpravu mapy zo simulátoru, napríklad kliknutím na príslušnú bunku.

**Balík (1b):** Vytvorte a nakonfigurujte balík, ktorý spustí všetko potrebné

