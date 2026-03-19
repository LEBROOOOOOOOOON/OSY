# Cvičenie 6: Aktualizácia, zabezpečenie OS Windows a systémové politiky

## Úloha 1: Windows Update

### 1.1 Pojmy

1. Čo je Windows Update a na čo slúži?

   → Windows Update je služba v systéme Windows, ktorá slúži na sťahovanie a inštaláciu aktualizácií systému, ovládačov a bezpečnostných opráv.

2. Čo znamená označenie KB (napr. KB5034441)?

   → KB (Knowledge Base) je identifikačné číslo konkrétnej aktualizácie od Microsoftu.

3. Vysvetlite rozdiel medzi aktualizáciou kvality (Quality) a aktualizáciou funkcií (Feature):

   → Aktualizácia kvality (Quality) obsahuje opravy chýb a bezpečnostné záplaty.  
   → Aktualizácia funkcií (Feature) pridáva nové funkcie a väčšie zmeny systému.

4. Prečo je nebezpečné neaktualizovať systém? Uveďte reálny príklad:

   → Neaktualizovaný systém je zraniteľný voči útokom.  
   → Príklad: WannaCry ransomware využil chybu vo Windows a napadol tisíce počítačov.

### 1.2 Praktická časť

**Otvorte** Nastavenia → Windows Update:

| Otázka | Odpoveď |
|--------|---------|
| Je systém aktuálny? (Áno/Nie) | Áno |
| Koľko aktualizácií čaká na inštaláciu? | 0 |
| Dátum poslednej nainštalovanej aktualizácie | 19. 11. 2025 |
| KB číslo poslednej aktualizácie | nevim|

**Spustite v CMD:** `wmic qfe list brief /format:table`

| Otázka | Odpoveď |
|--------|---------|
| Koľko aktualizácií vidíte vo výpise? | 51 |
| HotFixID poslednej aktualizácie |  KB5071982 |

**Otvorte** `services.msc` a nájdite službu Windows Update:

| Otázka | Odpoveď |
|--------|---------|
| Stav služby (Spustená/Zastavená) | Spustená |
| Typ spustenia (Automaticky/Ručne/Zakázané) | Automaticky |

5. Čo by sa stalo, keby ste typ spustenia služby Windows Update zmenili na "Zakázané"?

   → Systém by sa neaktualizoval a bol by zraniteľný voči bezpečnostným hrozbám.

---

## Úloha 2: Zabezpečenie Windows

### 2.1 Pojmy

1. Čo je Windows Defender?

   → Windows Defender je antivírusový program od Microsoftu, ktorý chráni počítač pred vírusmi a hrozbami.

2. Aký je rozdiel medzi rýchlym a úplným skenovaním?

   → Rýchly scan kontroluje základné oblasti systému.  
   → Úplný scan kontroluje celý disk a trvá dlhšie.

3. Čo je firewall a na čo slúži? Vysvetlite vlastnými slovami:

   → Firewall je ochrana, ktorá kontroluje sieťovú komunikáciu a blokuje nebezpečné pripojenia.

4. Windows firewall má 3 profily – vymenujte ich a napíšte, kedy sa ktorý aktivuje:

   - **Doménový:** keď je PC v doméne (firemná sieť)  
   - **Súkromný:** dôveryhodná sieť (napr. doma)  
   - **Verejný:** verejná sieť (napr. WiFi v škole/kaviarni)

5. Čo znamená príkaz `wf.msc` a čo `firewall.cpl`? Aký je medzi nimi rozdiel?

   → `wf.msc` otvára pokročilé nastavenia firewallu  
   → `firewall.cpl` otvára základné nastavenia firewallu  
   → Rozdiel je v tom, že wf.msc je detailnejší nástroj

### 2.2 Praktická časť

**Otvorte** Zabezpečenie systému Windows a zapíšte stav:

| Komponent | Stav (OK / Varovanie / Chyba) |
|-----------|-------------------------------|
| Ochrana pred vírusmi a hrozbami | OK |
| Firewall a ochrana siete | OK |

**Spustite v CMD:** `netsh advfirewall show allprofiles state`

| Profil | Stav (ON/OFF) |
|--------|---------------|
| Doménový | ON |
| Súkromný | ON |
| Verejný | ON |

6. Prečo by ste nemali firewall vypínať, aj keď vám niečo nefunguje? Čo by ste mali urobiť namiesto toho?

   → Firewall chráni systém pred útokmi.  
   → Namiesto vypnutia treba povoliť konkrétnu aplikáciu alebo port.

---

## Úloha 3: Lokálne politiky – gpedit.msc

### 3.1 Pojmy

1. Čo je gpedit.msc a na čo slúži?

   → gpedit.msc je nástroj na správu lokálnych politík Windows.

2. Aký je rozdiel medzi lokálnou politikou a doménovou politikou?

   → Lokálna politika platí pre jeden počítač.  
   → Doménová politika platí pre viac počítačov v sieti.

3. Čo robí príkaz `gpupdate /force`? Kedy ho musíte spustiť?

   → Aktualizuje politiky okamžite.  
   → Používa sa po zmene nastavení.

4. Čo robí príkaz `gpresult /r`?

   → Zobrazí aktuálne aplikované politiky.

5. Vysvetlite, čo je politika uzamknutia účtu a proti akému typu útoku chráni:

   → Uzamkne účet po viacerých neúspešných pokusoch.  
   → Chráni proti brute-force útoku.

### 3.2 Praktická časť – politiky hesiel

**Otvorte** gpedit.msc → Konfigurácia počítača → Nastavenia systému Windows → Nastavenia zabezpečenia → Politiky účtov → Politika hesiel

| Politika | Aktuálna hodnota |
|----------|-------------------|
| Minimálna dĺžka hesla | 0 |
| Maximálny vek hesla | 42 |
| Heslo musí spĺňať požiadavky na zložitosť | vypnute |
| Vynútiť históriu hesiel | vypnute |

6. Prečo je dôležité vynútiť históriu hesiel? Čo by sa stalo bez nej?

   → Zabráni opakovaniu rovnakých hesiel.  
   → Bez nej by používateľ mohol stále používať to isté heslo.

### 3.3 Praktická časť – uzamknutie účtu a CMD

- [x] Hotovo

| Otázka | Odpoveď |
|--------|---------|
| Čo sa stalo po pokuse otvoriť CMD? | CMD bolo zablokované |
| Funguje PowerShell naďalej? (Áno/Nie) | Áno |

- [x] Vrátené

---

## Bonusové scenáre (nepovinné)

### Scenár 1: Ransomware útok

1. Čo mal mať zapnuté, aby sa tomu predišlo? (2 veci)

   → Antivírus (Windows Defender)  
   → Firewall

2. Aký typ skenovania by ste spustili na ostatných PC?

   → Úplné skenovanie

### Scenár 2: Nový zamestnanec

1. Aký nástroj použijete? (_____.msc)

   → gpedit.msc

2. Napíšte celú cestu v gpedit.msc k politike minimálnej dĺžky hesla:

   → Konfigurácia počítača → Nastavenia systému Windows → Nastavenia zabezpečenia → Politiky účtov → Politika hesiel

3. Napíšte celú cestu k politike zakázania CMD:

   → Konfigurácia používateľa → Šablóny pre správu → Systém → Zabrániť prístupu k príkazovému riadku

4. Aký príkaz spustíte po zmene politík?

   → gpupdate /force

### Scenár 3: Podozrivá aktivita

1. O aký typ útoku ide?

   → Brute-force útok

2. Aká politika by tomu zabránila a aké hodnoty by ste nastavili?

   → Politika uzamknutia účtu  
   → napr. 5 pokusov, 30 minút uzamknutie