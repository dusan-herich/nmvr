# Zadanie 3

Toto zadanie otestuje vaše znalosti z algoritmov hľadania cesty. Vašou úlohou bude rozšírenie druhého zadania tak, aby sa Váš robot vedel samostatne pohybovať a vyhýbať sa prekážkam. Úspešné splnenie všetkých požiadaviek vám zaručí 5 bodov. Riešiť ho môžete do **16.12.2021** kedy ho budete obhajovať a demonštrovať jeho funkčnosť. Zdrojové kódy musia byť odovzdané vo vašom repozitári. Na riešenie úloh môžete použiť akýkoľvek programovací jazyk, avšak ROS2 samotný disponuje knižnicami len pre **Python** a **C++**.



Pri riešení si zvoľte jednu implementáciu predchádzajúcich zadaní vaše skupiny. Je odporúčané používať vedeckú literatúru (prístup prostredníctvom VPN). Obhajoba bude pozostávať nielen z vysvetlenia implementácie, ale aj z vysvetlenia princípov algoritmu D\* Lite.



## Do vášho simulátora doplníte

**Implementáciu algoritmu D\* Lite:**  Tento algoritmus sa bude starať o hľadanie cesty medzi dvomi bodmi tak, aby sa robot dokázal vyhnúť prekážkam. Nezabúdajte na to, že prekážky môžu byť dynamické, teda ich prítomnosť na mape sa môže časom meniť a cesta, ktorá bola naplánovaná pôvodne už nemusí byť vhodná.

**Vizualizácie:** V simulátore musí byť znázornená trajektória, ktorú má robot sledovať. Ak sa trasa kvôli nečakaným prekážkam zmení a nájde sa nová cesta, musí byť vyznačená inak ako pôvodná.