# Souboj s kostkou proti počítači

Vytvoř konzolovou hru, ve které hráč soutěží proti počítači. V každém kole se hráč i počítač pokusí odhadnout výsledek hodu klasickou šestistěnnou kostkou.

Cílem hry je jako první získat **5 bodů**.

## Pravidla hry

Na začátku každého kola si hráč vybere jednu ze tří možností:

```text
1. Padne méně než 3
2. Padne přesně 3
3. Padne více než 3
```

Počítač si jednu z těchto možností vybere náhodně.

Poté program náhodně vygeneruje hod šestistěnnou kostkou, tedy číslo od **1 do 6**.

Body se přidělují následovně:

- správný tip **méně než 3** → **1 bod**
- správný tip **přesně 3** → **2 body**
- správný tip **více než 3** → **1 bod**
- chybný tip → **0 bodů**

Hráč i počítač mohou v jednom kole získat body, pokud si vybrali stejnou správnou možnost.

## Průběh jednoho kola

Program může například vypsat:

```text
---------------------
Options:
1. Lower than 3
2. Exactly 3
3. Higher than 3
---------------------

Pick an option (1-3): 2

---------------------
You have chosen option 2
AI has chosen option 3
Dice roll: 3

Adding 2 to player
Adding 0 to AI

Score:
Player: 2
AI: 0
---------------------
```

Po skončení kola začne automaticky další kolo.

## Požadavky

Program musí:

1. Uchovávat aktuální počet bodů hráče a počítače.
2. Opakovat jednotlivá kola, dokud hráč nebo počítač nezíská **5 bodů**.
3. Kontrolovat vstup hráče pomocí `int.TryParse()`.
4. Pokud hráč zadá něco jiného než číslo `1`, `2` nebo `3`, program ho musí vyzvat k novému zadání.
5. Náhodně generovat:
   - volbu počítače `1–3`
   - hod kostkou `1–6`
6. Po každém kole vypsat:
   - volbu hráče
   - volbu počítače
   - výsledek hodu kostkou
   - počet získaných bodů
   - aktuální celkové skóre
7. Po skončení hry oznámit vítěze.

## Rozdělení programu do metod

Program nerozděluj celý pouze do `Main()`. Použij alespoň následující metody:

```csharp
static void PrintOptions()
```

Vypíše hráči dostupné možnosti.

```csharp
static int PickOption()
```

Načte a zkontroluje volbu hráče. Vrátí číslo `1–3`.

```csharp
static int ThrowDice()
```

Vrátí náhodný hod kostkou `1–6`.

```csharp
static int AI()
```

Vrátí náhodnou volbu počítače `1–3`.

```csharp
static int Evaluate(int diceRoll, int choice)
```

Podle hodu kostkou a zvolené možnosti rozhodne, kolik bodů hráč nebo počítač získal.

## Bonus

Pokud základní verze funguje, můžete přidat například:

- možnost nastavit počet bodů potřebných k vítězství
- počet odehraných kol
- statistiku úspěšnosti hráče
- možnost hrát další hru bez restartování programu
- slovní výpis volby místo čísla, například:

```text
Player chose: Exactly 3
AI chose: Higher than 3
```
