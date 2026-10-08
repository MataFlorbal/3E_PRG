# Test – 3E A1

**Datum:** 8. 10. 2026

- **Čas:** celá hodina
- **Odevzdání:** Outlook s předmětem: `3E_A1_Test`
  - soubor: `Program.cs`
- **Pomůcky:**
  - Zakazuje se umělá inteligence, spolupráce, existující řešení.

> [!IMPORTANT]
> Všechny úkoly budou vypracovány jako samostatné metody

## 1. Herní obchod

Napište metodu, která akceptuje cenu předmětu, procentuální slevu a **vrátí** výslednou cenu po slevě pomocí vzorce:

$$
s = \frac{c \cdot p}{100}
$$

$$
v = c - s
$$

Kde:

- `c` – původní cena předmětu,
- `p` – procentuální sleva,
- `s` – výše slevy,
- `v` – výsledná cena předmětu.

---

## 2. Těžba surovin

Hráč potřebuje nasbírat určité množství železa pro výrobu zbroje. Každý den vytěží stejné množství železa a ukládá ho do skladu.

Napište program, který načte:

- požadované množství železa,
- množství železa vytěženého za jeden den.

Pomocí cyklu postupně zvyšujte množství nasbíraného železa a po každém dni vypište, kolik železa ještě zbývá vytěžit.

Program skončí ve chvíli, kdy hráč nasbírá požadované množství železa.

Příklad:

```text
Požadované množství železa: 100
Těžba za den: 30

Den 1: zbývá vytěžit 70
Den 2: zbývá vytěžit 40
Den 3: zbývá vytěžit 10
Den 4: požadované množství bylo vytěženo

Železo jste nasbírali za 4 dny.
```

Program by neměl vypisovat záporné množství zbývajícího železa.

---

## 3. Hodnocení postavy

Napište program, který od uživatele načte hodnoty tří vlastností herní postavy: `síla`, `obratnost` a `inteligence`.

Nejprve zjistěte, zda jsou všechny hodnoty platné.

Každá vlastnost musí mít hodnotu od 1 do 20 včetně.

Pokud některá hodnota není platná, vypište:

```text
Neplatné hodnoty vlastností postavy.
```

Pokud jsou všechny hodnoty platné, určete typ postavy podle jejich hodnot:

- všechny tři vlastnosti jsou stejné → vyvážená postava,
- právě dvě vlastnosti jsou stejné → specializovaná postava,
- všechny vlastnosti jsou různé → různorodá postava.

Příklad:

```text
Síla: 15
Obratnost: 15
Inteligence: 10

Hodnoty vlastností jsou platné.
Jedná se o specializovanou postavu.
```
