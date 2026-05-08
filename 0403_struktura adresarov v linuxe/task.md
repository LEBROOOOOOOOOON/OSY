# Cvičenie: Štruktúra adresárov v Linuxe + POSIX

> Vyplň odpovede pod každú otázku. Pri otázkach typu áno/nie zaškrtni `- [x]`. Výstupy z terminálu prilep do code blokov.
> **Dnes nič nemažeme ani nemeníme** — iba pozeráme.

---

## Úloha 1 — Programy v systéme

### 1.1 Spusti `ls /bin | head` a vymenuj **5 príkazov**, ktoré poznáš:

-apt
-apg
-apt -get
-7z
-HEAD

### 1.2 Spusti `which ls`. Kde reálne leží `ls`?

```
usr/bin/ls
```

### 1.3 Spusti `which` s nejakým iným programom (napr. `python3`, `nano`, `firefox`):

```bash
which __________
```

**Výstup:**

```
/usr/bin/firefox
```

### 1.4 Aký je rozdiel medzi `/bin` a `/sbin`?

> *(Stačí jedna veta.)*

---sbin je iba pre spravcu.

## Úloha 2 — Konfigurácie a používatelia

### 2.1 Spusti `cat /etc/hostname`. Ako sa volá tvoj počítač?

```
mint
```

### 2.2 Spusti `cat /etc/passwd | grep $USER`. Skopíruj **celý riadok**:

```
mint:x:1000:1000:Live session user,,,:/home/mint:/bin/bash
```

### 2.3 Z tohto riadku zisti:

- **UID** (tretie pole, oddelené ``):1000
- **Shell** (posledné pole):/bin/bash
- **Domov** (predposledné pole):/home/mint:

### 2.4 Aké **používateľské meno** má UID 0?

> *(Tip: pozri prvý riadok `/etc/passwd`.)*

---mint

## Úloha 3 — Prieskum systému

> Pre tieto úlohy nepotrebuješ `sudo` — všetko je verejne čitateľné.

### 3.1 Aký máš procesor? Spusti:

```bash
cat /proc/cpuinfo | grep "model name" | head -1
```

```

```

### 3.2 Koľko máš RAM? Spusti:

```bash
cat /proc/meminfo | head -3
```

```

```

### 3.3 Ako dlho beží systém? Spusti `uptime`:

```

```

### 3.4 Vymenuj **3 logy**, ktoré nájdeš v `/var/log/`:

```bash
ls /var/log/ | head
```

-
-
-

### 3.5 Aké disky / partície máš? Spusti:

```bash
ls /dev | grep sd
```

```

```

### 3.6 Bonus — spusti `uname -a` a zapíš výstup:

```

```

---

## Úloha 4 — POSIX v praxi

### 4.1 Funguje `ls -la` aj na **macOS**?

- [ ] áno
- [ ] nie

### 4.2 Funguje `ls -la` v **CMD na Windowse** (bez WSL)?

- [ ] áno
- [ ] nie

### 4.3 Prečo rovnaký bash skript beží na **Linuxe aj na MacBooku**?

> *(Vlastnými slovami, jedna-dve vety.)*

### 4.4 Vymenuj **2 OS**, ktoré sú POSIX-kompatibilné (okrem Linuxu):

1.
2.

### 4.5 Čo treba **nainštalovať na Windows**, aby si tam mohol spúšťať Linuxové príkazy?

---

## Úloha 5 — Orientácia v cudzom systéme

> Predstav si, že ti práve dali SSH prístup na **neznámy server**. Bez toho, aby si **čokoľvek menil**, zisti tieto informácie.

### 5.1 Aká je distribúcia? Spusti:

```bash
cat /etc/os-release | head -3
```

```

```

### 5.2 Si root alebo bežný používateľ? Spusti `whoami`:

```

```

### 5.3 Koľko používateľov má účet v `/home`? Spusti `ls /home`:

```

```

### 5.4 Aká verzia jadra beží? Spusti `uname -r`:

```

```

### 5.5 **Vlastnými slovami:** aké **3 príkazy** spustíš ako prvé na novom Linuxe, aby si zistil, kde si?

1.
2.
3.

---

## Bonus — interaktívne otázky

### B.1 Skús zistiť, **koľko procesorových jadier** máš:

```bash
nproc
```

Výstup:

```

```

### B.2 Skús `df -h /` — koľko miesta máš na koreňovom disku?

```

```

### B.3 Aký súbor v `/etc` ti **najviac zaujal** a prečo?

---

## Záver

### Z dnešnej hodiny — ktorý adresár si **najlepšie zapamätáš** a prečo?

### Aký bol **najprekvapivejší** poznatok dnešnej hodiny?