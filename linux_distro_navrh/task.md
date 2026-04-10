# Ako spustiť Linux na starých/slabých PC (napr. 312 počítačoch)

Tento dokument sumarizuje štyri najlepšie spôsoby, ako spustiť Linux na starších alebo slabších počítačoch, kde výkon je obmedzený. Cieľom je minimalizovať záťaž na RAM a CPU a umožniť plynulé používanie Linuxu.

---

## 1. VirtualBox s ľahkým Linuxom

**Popis:**  
VirtualBox umožňuje spustiť Linux ako virtuálny stroj vo Windows bez nutnosti dualbootu. Vhodné pre počítače s aspoň 1 GB RAM.

**Odporúčané distribúcie:**
- Lubuntu (LXQt) – ľahké, stabilné
- Xubuntu (XFCE) – šetrné na RAM
- Puppy Linux – extrémne ľahký, veľmi rýchly

**Postup:**
1. Nainštaluj [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
2. Stiahni ISO vybranej Linux distribúcie.
3. Vytvor nový virtuálny stroj:
   - RAM: 1–2 GB (viac, ak je dostupné)
   - Disk: 10–20 GB
4. Pripoj ISO ako boot disk a spusti inštaláciu.

**Tip:** Pre PC s menej ako 2 GB RAM je Puppy Linux najplynulejšia voľba.

---

## 2. Bootable USB (Live USB alebo Full Install)

**Popis:**  
Linux môžeš spustiť priamo z USB kľúča alebo ho nainštalovať na disk vedľa Windows (dualboot). Ideálne pre veľmi starý hardvér.

**Odporúčané distribúcie:**  
- Lubuntu, Xubuntu, Puppy Linux, Tiny Core Linux

**Postup:**
1. Stiahni ISO ľahkého Linuxu.
2. Použi [Rufus](https://rufus.ie/) alebo [BalenaEtcher](https://www.balena.io/etcher/) na vytvorenie bootovacieho USB.
3. Reštartuj počítač a vyber boot z USB.

**Výhoda:** Minimálna záťaž na systém, Linux ide priamo z USB, bez inštalácie.

---

## 3. Portable Linux (frugal install)

**Popis:**  
Linux nainštalovaný priamo na USB alebo malý oddiel, spúšťa sa bez plnej inštalácie. Veľmi vhodné pre slabé PC.

**Odporúčané distribúcie:**  
- Puppy Linux, Slax

**Výhoda:**  
- Rýchly štart  
- Nenáročný na RAM a CPU  
- Prenositeľný medzi počítačmi

---

## 4. Minimal Linux v VirtualBoxe (bez GUI)

**Popis:**  
Inštalácia Linuxu bez grafického rozhrania (iba terminál). Extrémne šetrné na systémové zdroje, ideálne pre slabý hardware alebo testovanie veľkého množstva PC.

**Odporúčané distribúcie:**  
- Debian NetInstall  
- Tiny Core Linux  
- Arch Linux minimal

**Postup:**  
1. Stiahni minimálny ISO obraz distribúcie.  
2. Vytvor VirtualBox VM s nízkou RAM (512 MB – 1 GB) a malým diskom (5–10 GB).  
3. Spusti inštaláciu a vynechaj GUI.  

**Výhoda:**  
- Veľmi rýchly a ľahký  
- Ideálne pre experimenty a školské laby s množstvom starých PC  

---

**Tipy pre všetky možnosti:**
- Preferuj ľahké desktopové prostredia: **LXQt, XFCE, MATE**  
- Pre PC s <2 GB RAM je najlepšia voľba Puppy Linux alebo textový Linux  
- Použitie USB alebo Live CD minimalizuje riziko poškodenia Windows systému