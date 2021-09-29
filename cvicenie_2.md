# 1 Uzly

V tomto cvičení sa oboznámite s konceptom uzlov (nodes) a tém (topics), čo sú základné koncepty ROS2, ktoré spolu vytvárajú ROS graf. Všetky koncepty si vysvetlíme na jednoduchom simulátore Turtlesim, ktorý spustíme nasledovným príkazom

```bash
ros2 run turtlesim turtlesim_node
```

Tento príkaz otvorí okno so simulátorom a zároveň vytvorí nový uzol v grafe. Každý z týchto uzlov má priradené meno. Ak toto meno potrebujeme zistiť, použijeme príkaz:

```
ros2 node list
```

ktorý zobrazí názvy všetkých, práve bežiacich uzlov. Vo výstupe bude jediný uzol, prislúchajúci simulátoru, a to:

```
/turtlesim
```

Aby sme mohli simulátor vyskúšať, musíme spustiť ďalší uzol, tentokrát taký, ktorý bude korytnačku ovládať "diaľkovo". Pôvodné okno s terminálom ponechajte otvorené a otvorte nové, v ktorom použijete:

```
ros2 run turtlesim turtle_teleop_key
```

> Všimnite si podobnosť príkazov pri spúšťaní uzlov. Prvá časť je rovnaká, pretože oba uzly existujú v jednom balíku.

Teraz skontrolujte zoznam uzlov, ktoré ROS 2 eviduje. Použitím správneho príkazu získate nasledovný výstup:

```
/turtlesim
/teleop_turtle
```

Stláčaním šípok môžete korytnačku ovládať. Ak vidíte pohyb aj jej trajektóriu, spustite ďalšiu inštanciu Turtlesim a nechajte si vypísať zoznam uzlov. Stláčajte šípky, aby začala korytnačka vykonávať pohyb. Aké správanie pozorujete a pokúste sa vysvetliť prečo.

Každý z uzlov má určitú množinu vlastností, ktorá definuje jeho správanie a môžeme ich prezerať pomocou príkazu:

```
ros2 node info <node_name>
```

Zistite, aké vlastnosti má uzol simulátora. Rovnaký príkaz použite pre */teleop_turtle* a porovnajte výstupy.

Vlastnosti môžeme meniť pomocou takzvaného "remappingu". 

```
ros2 run turtlesim turtlesim_node --ros-args --remap __node:=my_turtle
```

Teraz opäť vypíšte mená všetkých uzlov a porovnajte výstupy pred remappingom a po ňom.

# 2 Témy

Zatvorte všetky okná terminálu so spustenými uzlami a spustite nové inštancie *turtlesim* ako aj teleoprerácie.  Keď sa oba uzly spustia, použite príkaz:

```
rqt_graph
```

v novom okne terminálu. Tento nástroj umožňuje vizualizovať uzly, témy a prepojenia medzi nimi. Graf, ktorý práve vidíte zobrazuje tok komunikácie, medzi oboma uzlami pomocou tém - uzol *teleop_turtle* publikuje dáta do témy *turtle1/cmd_vel* a uzol */turtlesim* tieto dáta počúva.

> Všimnite si, že v témach je použitý delimiter "/", vďaka ktorému je možné simulovať hierarchiu

Podobne ako pri uzloch, ROS 2 môže vypísať aj zoznam registrovaných tém. Príkaz skúste odvodiť podľa predošlej sekcie. Každá z tém má navyše aj typ (koncept ako pri premenných v programovaní). Aby sme zistili typ témy, stačí za príkaz, pridať parameter *-t*. Akého typu je téma */turtle1/cmd_vel*?

V dalšom kroku budeme sledovať, aké dáta sú v téme publikované.  Doplňte príkaz tak, aby vám zobrazoval dáta o rýchlosti korytnačky:

```
ros2 topic echo <doplnte>
```

Teraz ovládajte korytnačku a sledujte výstupy príkazu.

Rovnako ako pri uzloch, informácie je možné zistiť aj o jednotlivých témach. Opäť sa pokúste vhodne upraviť príkaz oproti predošlej sekcii. Vo výstupe si všimnite počty publisherov a subscriberov. V ROS2 komunikácia nemusí byť len vo vzťahu one-to-one, ale aj one-to-many, prípadne many-to-many.

Uzly si zasielajú dáta prostredníctvom správ. Aby ich komunikácia fungovala, publisher aj subscriber musia prijímať/posielať rovnaké typy správ. Typy tém, ktoré sme zisťovali už skôr určujú práve aký druh správy je použitý na konkrétnej téme.

Každý typ správy má definovanú istú štruktúru. Ak ju potrebujeme zistiť, stačí v príkazovom riadku zadať:

```
ros2 interface show typ_spravy
```

Zistite, akú štruktúru má správa typu geometry_msgs/msg/Twist. Teraz, keď nám je známa štruktúra správy, môžeme do nej publikovať dáta aj priamo z príkazového riadku:

```
ros2 topic pub --once <nazov_temy> <typ_spravy> "data"
```

Pokúste sa s korytnačkou opísať štvorec.

> Hint: Dáta formátujte do slovníka

Posledný koncept s ktorým sa dnes oboznámite je frekvencia publikovania dát. Zvoľte si ľubovoľnú tému a príkazom:

```
ros2 topic hz <tema>
```

zistite minimálny, maximálny a priemerný čas.  

Teraz môžete zatvoriť všetky inštancie terminálu.