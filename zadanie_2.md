# Zadanie 2

Toto zadanie otestuje vaše znalosti odometrie, riadenia a ROS2. Vašou úlohou bude rozšírenie prvého zadania tak, aby sa Váš robot vedel samostatne pohybovať. Úspešné splnenie všetkých požiadaviek vám zaručí 5 bodov. Riešiť ho môžete do **25.10.2021** kedy ho budete obhajovať a demonštrovať jeho funkčnosť. Zdrojové kódy musia byť odovzdané vo vašom repozitári. Na riešenie úloh môžete použiť akýkoľvek programovací jazyk, avšak ROS2 samotný disponuje knižnicami len pre **Python** a **C++**.

## Do vášho simulátora doplníte:

**Vhodné premenné, uzly a témy (1b):** Objektu vášho robota pridajte premenné pre rýchlosť, polohu a otočenie. Ak si to bude vaša implementácia vyžadovať, pridajte ľubovoľné témy a uzly.

**Regulátor (2b)** : Doplňte implementáciu regulátora PID (postačuje len P zložka), tak aby vedel pohybovať robotom po mriežkovej mape medzi dvoma bodmi ak medzi nimi nie je prekážka.

**Určovanie polohy (2b):** Implementujte algoritmus určovania polohy pomocou odometrie. Všetky potrebné vstupy musia byť získavané z doplnených premenných.