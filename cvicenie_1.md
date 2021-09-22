

# 1 HYPERVÍZOR

Pre prácu na cvičeniach budeme používať Linux. Ak ho už v súčasnosti nepoužívate, ani naň nechcete trvalo prejsť [:)], budete používať virtuálny stroj. Stiahnite a nainštalujte si, napríklad [Virtualbox](https://www.virtualbox.org/wiki/Downloads). Ak preferujete inú aplikáciu, môžete použiť aj tú. Nezabudnite však zvoliť vhodného host-a. 

# 2 OPERAČNÝ SYSTÉM

Na cvičeniach aj zadaniach budeme používať ROS2 vo verzii Galactic Geochelone. Aby ste zabezpečili jeho správny a bezproblémový beh, je potrebné ho nainštalovať na distribúcii Ubuntu 20.04 Focal Fossa. Použiť môžete aj niektorú z jej “flavours”, napríklad [Xubuntu](https://xubuntu.org/news/xubuntu-20-04-released/).

## 2.1 Inštalácia

Pred samotnou inštaláciou je potrebné vytvoriť virtuálny stroj. Nakonfigurujte ho tak, aby spĺňal tieto požiadavky:

- Najmenej 4096MB RAM
- Virtuálny disk s dynamickou alokáciou do 50GB

Následne môžete spustiť inštaláciu operačného systému, dbajte aby ste systém nainštalovali podľa nasledovných podmienok:

- Locale ponechajte v angličtine, rozloženie klávesnice QWERTY
- Nesťahovať aktualizácie pri inštalácii
- Neinštalovať softvér tretích strán
- Vymazať disk (virtuálneho stroja, neprídete o vaše dáta) a nainštalovať Xubuntu
- Meno, názov zariadenia, používateľské meno aj heslo nastavte na "nmvr"
- Povoľte automatický login



# 3 ROS2

V tomto kroku sa budeme venovať inštalácii ROSu. Vo vytvorenom virtuálnom stroji si otvorte shell a skontrolujte, či je povolený Ubuntu universe repository.

```shell
apt-cache policy | grep universe
```

Po spustení by ste mali vo výstupe nájsť nasledovné.

```shell
500 http://us.archive.ubuntu.com/ubuntu focal/universe amd64 Packages
     release v=20.04,o=Ubuntu,a=focal,n=focal,l=Ubuntu,c=universe,b=amd64
```

Ak ste tento riadok našli, môžete pokračovať ďalej. Pokiaľ tento riadok vo výstupe chýba, musíte povoliť universe repository.

```shell
sudo apt install software-properties-common
sudo add-apt-repository universe
```

Teraz môžete pokračovať pridaním apt repozitára ROS2. Najskôr je nutné autorizovať GPG kľúč.

```shell
sudo apt update && sudo apt install curl gnupg lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg
```

Potom môžete pridať repozitár do zoznamu.

```shell
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

Posledným krokom pred spustením inštalácie je update

```shell
sudo apt update
```

Inštalácia začne týmto príkazom.

```shell
sudo apt install ros-galactic-desktop
```

# 4 Nastavenie prostredia

Týmto jednoduchým krokom je potrebné nastaviť prostredie. Stačí použiť jediný príkaz

```shell
source /opt/ros/galactic/setup.bash
```

# 5 Overenie inštalácie

