## Úloha 1 – Čtení kláves z klávesnice

Vytvořte jednoduchý konzolový program, který bude reagovat na stisk klávesy.

Program:

1. Vyzve uživatele ke stisknutí libovolné klávesy.
2. Načte stisknutou klávesu pomocí `Console.ReadKey()`.
3. Vypíše, která klávesa byla stisknuta.

Příklad výstupu:

```text
Stiskněte libovolnou klávesu:

Stiskli jste klávesu: W
```

Následně program upravte tak, aby rozpoznával klávesy `W`, `A`, `S` a `D`.

Pro jednotlivé klávesy vypište odpovídající směr:

```text
W -> nahoru
S -> dolů
A -> doleva
D -> doprava
```

Pokud uživatel stiskne jinou klávesu, vypište:

```text
Neznámá klávesa.
```

Vyzkoušejte také rozdíl mezi:

```csharp
Console.ReadKey();
```

a:

```csharp
Console.ReadKey(true);
```

---

## Úloha 2 – Reakční test

Vytvořte jednoduchý program, který změří reakční čas uživatele.

Po spuštění program vypíše:

```text
=== REAKČNÍ TEST ===

Připravte se...
```

Program poté počká náhodně dlouhou dobu, například 1 až 4 sekundy.

Po uplynutí této doby vypíše:

```text
TEĎ!
```

Vaším úkolem je co nejrychleji stisknout klávesu `SPACE`.

Program změří dobu mezi zobrazením textu `TEĎ!` a stisknutím mezerníku.

Příklad:

```text
=== REAKČNÍ TEST ===

Připravte se...

TEĎ!

Váš reakční čas: 284 ms
```

Pro měření času můžete využít třídu `Stopwatch`.

Pro náhodnou dobu čekání použijte `Random`.

Program by měl reagovat pouze na klávesu `SPACE`.

### Rozšíření

Pokud budete hotovi dříve, upravte program tak, aby:

- provedl 3 reakční testy,
- po každém pokusu vypsal naměřený čas,
- na konci vypsal nejlepší dosažený čas.

Příklad:

```text
Pokus 1: 312 ms
Pokus 2: 275 ms
Pokus 3: 301 ms

Nejlepší čas: 275 ms
```

---

## Úloha 3 – Zamčené dveře

Vytvořte jednoduchou simulaci otevírání zámku pomocí paklíče.

Zámek má správnou pozici v rozsahu `1 až 10`. Správnou pozici program na začátku náhodně vygeneruje.

Hráč začíná s paklíčem například na pozici `5`.

Ovládání:

```text
A       posun paklíče doleva
D       posun paklíče doprava
SPACE   pokus o odemknutí
Q       ukončení programu
```

Program vždy vypíše aktuální pozici paklíče:

```text
=== ZAMČENÉ DVEŘE ===

Pozice paklíče: 5

A - doleva
D - doprava
SPACE - pokus o odemknutí
Q - konec
```

Pomocí kláves `A` a `D` můžete měnit pozici paklíče.

Paklíč se nesmí dostat mimo rozsah `1 až 10`.

Pokud stisknete `SPACE`, program porovná aktuální pozici paklíče se správnou pozicí zámku.

Podle vzdálenosti vypíše nápovědu:

```text
Správná pozice             -> Zámek je otevřený.
Vzdálenost 1               -> Jste velmi blízko.
Vzdálenost 2 až 3          -> Zámek se trochu pohnul.
Větší vzdálenost           -> Zámek se ani nehne.
```

Příklad průběhu:

```text
Pozice paklíče: 5

SPACE

Zámek se trochu pohnul.
```

Po několika pokusech:

```text
Pozice paklíče: 8

SPACE

Zámek je otevřený.
```

Po úspěšném otevření zámku program skončí.

### Rozšíření

Pokud budete hotovi dříve, můžete doplnit například:

- omezený počet pokusů o odemknutí,
- počet zlomených paklíčů,
- několik různě obtížných zámků,
- metodu, která bude vyhodnocovat pokus o otevření,
- počítání počtu tahů potřebných k otevření zámku.
