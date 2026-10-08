# Test

- čas: celá hodina
- odevzdání: outlook s předmětem: 3E_A2_Test
  - soubor: `Program.cs`
- Pomůcky: 
  - Zakazuje se umělá inteligence, spolupráce, existující řešení.

## 1. Herní obchod

Napište metodu, která akceptuje strany trojúhelníku a **vrátí** výsledek pomocí vzorce:


$$s=\frac{a+b+c}{2}$$


$$S=\sqrt{s(s-a)(s-b)(s-c)}$$

---

## 2. Splácení dluhu

Hráč dluží obchodníkovi určité množství zlaťáků. Každý den vydělá stejný počet zlaťáků a všechny použije na splácení dluhu.

Napište program, který načte:

- počáteční výši dluhu,
- počet zlaťáků vydělaných za jeden den.

Pomocí cyklu postupně snižujte výši dluhu a po každém dni vypište, kolik zlaťáků ještě zbývá splatit.

Program skončí ve chvíli, kdy je celý dluh splacen.

Příklad:

```text
Výše dluhu: 100
Výdělek za den: 30

Den 1: zbývá splatit 70
Den 2: zbývá splatit 40
Den 3: zbývá splatit 10
Den 4: dluh byl splacen

Dluh jste splatili za 4 dny.
```

Program by neměl vypisovat zápornou výši dluhu.

---

## 3. Trojúhelník

Napište program, který od uživatele načte délky tří stran trojúhelníku `a`, `b` a `c`.

Nejprve zjistěte, zda z těchto stran může vzniknout trojúhelník.

Trojúhelník existuje pouze tehdy, pokud platí všechny následující podmínky:

```text
a + b > c
a + c > b
b + c > a
```

Pokud trojúhelník neexistuje, vypište:

```text
Z těchto stran nelze sestavit trojúhelník.
```

Pokud trojúhelník existuje, určete jeho typ podle délek stran:

- všechny tři strany jsou stejné → rovnostranný trojúhelník,
- právě dvě strany jsou stejné → rovnoramenný trojúhelník,
- všechny strany jsou různé → různostranný trojúhelník.

Příklad:

```text
Strana a: 5
Strana b: 5
Strana c: 8

Trojúhelník lze sestavit.
Jedná se o rovnoramenný trojúhelník.
```
