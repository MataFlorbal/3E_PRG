# Úvodní hodina

---

## Proč C# a co je to .NET?

-   **C# = jazyk** (silné typy, `async/await`, LINQ, records, pattern matching).

-   **.NET = platforma** (běhové prostředí CLR + standardní knihovny + SDK nástroje jako `dotnet` CLI; frameworky: ASP.NET Core, EF Core, MAUI…).

-   **Cross-platform**: Windows, Linux, macOS; **open-source**; bohatý ekosystém **NuGet**.

-   **Praxe**: webová API, enterprise systémy, cloud (Azure/AWS/GCP), desktop, mobil (MAUI), hry (Unity).

---

## Opakování z minulého roku

*(rozdíly vůči Javě)*

-   **Výstup/vstup**

    -   Java: `System.out.println(...)`, `Scanner`

    -   C#: `Console.WriteLine(...)`, vstup `Console.ReadLine()` → **vrací `string?`** (může být `null`).

-   **Parsování čísel**

    -   Java: `Integer.parseInt(s)`

    -   C#: `int.Parse(s)` / bezpečné si ukážeme později (`int.TryParse(s, out var x)`)

-   **Náhoda**

    -   Java: `new Random().nextInt(6) + 1`

    -   C#: `new Random().Next(1, 7)` *(horní mez je **exkluzivní**)*.

-   **Řetězce**

    -   Java: `equals()` porovnává obsah

    -   C#: `==` porovnává **obsah řetězce** (přívětivější než v Javě).

    -   Interpolace: `$"Ahoj, {jmeno}"` (v Javě `String.format` nebo `+`).

-   **`Main` a top-level**

    -   Java: vždy `public static void main(String[] args)`

    -   C#: může být **top-level** (bez viditelného `Main`) nebo klasický `Main`.


---

## Proměnné

-   Deklarace a typy (základ: `int`, `double`, `bool`, `char`, `string`).

-   `var` = (kompilátor odvodí typ z pravé strany).

-   Konvence: v C# **PascalCase** pro metody/třídy, **camelCase** pro místní proměnné.

-   **Nullable reference types**: `string?` může být `null` _(prázdná hodnota)_ → pomáhá odhalit chyby s `null`.


**Příklad:**

```csharp
Console.Write("Zadej věk: ");
string? input = Console.ReadLine();      // může být null
int inputAsNumber = int.Parse(input)

Console.WriteLine($"Za rok ti bude {vek + 1}.");
```

**Pozor rozdíly vůči Javě:**

-   `==` na řetězcích porovnává obsah (v Javě by to byla chyba).

-   Desetinná tečka/čárka: pro začátek pracujme s **celými čísly**; u desetinných řeší kultura (neřešme hned).


**Mini-úkoly (5–7 min):**

1.  Načti jméno a vypiš „Ahoj, …“.

2.  Načti dvě celá čísla a vypiš jejich součet.

3.  Načti celé `n` a vypiš `n²` (bez `Math.Pow` – použij násobení).


---

## Podmínky

-   `if`, `else if`, `else` – shodné principy jako v Javě.

-   Operátory: `==`, `!=`, `<`, `>`, `<=`, `>=`, `&&`, `||`, `!`.

-   `switch` v C# má i **výrazovou** podobu (zatím stačí klasický `switch`).


**Příklad:**

```csharp
Console.Write("Zadej známku (1-5): ");
if (int.TryParse(Console.ReadLine(), out int z))
{
    if (z == 1) {
        Console.WriteLine("Výborně");
    }
    else if (z <= 3) {
        Console.WriteLine("Prospěl/a");
    }
    else { 
        Console.WriteLine("Zkus to znovu");
    } 
}
```

**Mini-úkoly (5–7 min):**

1.  Zjisti, zda je číslo sudé/liché.

2.  Vstup věk → jestli je ≥ 18, vypiš „plnoletý/á“.

3.  Vstup heslo → pokud je délka < 6, „slabé“, jinak „ok“.


---

## Cykly

-   `while`, `do … while`, `for` – podobné jako v Javě.

-   `foreach` pro průchod kolekcí (ukážeme později s `Polem`).

-   Pozor na **nekonečné cykly** a správnou aktualizaci čítačů.


**Příklad (součet 1..n):**

```csharp
Console.Write("n: ");
int n = 100;
int sum = 0;

for (int i = 1; i <= n; i++){ 
       sum += i;
}

Console.WriteLine($"Součet 1..{n} = {sum}");

```

**Náhoda + cyklus (hádej číslo):**

```csharp
var rng = new Random();
int tajne = rng.Next(1, 101); // 1..100 (100 je EXKLUZIVNÍ horní mez)
int pokusy = 0;
int vstup = 0;
while (true)
{
    Console.Write("Tipni (1-100): ");
    vstup = int.Parse(Console.ReadLine());

    pokusy++;
    if (tip == tajne) { Console.WriteLine($"Správně! Na {pokusy}. pokus."); break; }
    Console.WriteLine(tip < tajne ? "Více ↑" : "Méně ↓");
}
```

**Mini-úkoly (7–10 min):**

1.  Vypiš násobilku pro zadané číslo (1× až 10×).

2.  Spočítej počet samohlásek ve větě (stačí `a,e,i,o,u,y` v malých).

3.  Generuj 10 náhodných čísel 1..6 a vypiš jejich průměr (celé dělení ne! použij `double`).


---

## Metody

-   Deklarace: návratový typ + jméno + parametry.

-   Volání metod, návratové hodnoty, základní přetížení.

-   V C# lze psát **výrazové tělo**: `int Soucet(int a, int b) => a + b;`


**Příklad:**

```csharp
static int Soucet(int a, int b) => a + b;

static bool JeSamohlaska(char c)
{
    c = char.ToLower(c);
    return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' || c == 'y';
}

static int PocetSamohlasek(string text)
{
    int pocetSamohlasek = 0;
    foreach (char znak in text) {
        if (JeSamohlaska(ch)) {
            pocetSamohlasek++;
        }
    }
    return pocetSamohlasek;
}

Console.WriteLine(Soucet(3, 4));
Console.WriteLine(PocetSamohlasek("Ahoj svete"));
```

**Pozor na rozdíly vůči Javě:**

-   `string` je **referenční typ** a je **neměnný**, stejně jako v Javě – ale porovnání obsahu je `==`.

-   `Console.ReadLine()` → `string?` (může být `null`), proto často **`?`** v typu a ošetření `null`.


**Mini-úkoly (7–10 min):**

1.  Napiš metodu `Max3(int a, int b, int c)`, která vrátí největší číslo.

2.  Napiš metodu `Reverse(string s)` vracející obrácený řetězec (bez vestavěných zkratek).

3.  Napiš metodu `JePrvocislo(int n)` a otestuj ji na prvních 30 číslech.


---

# Mini tahák: Java ➜ C#

| Java                                                     | C#                                                       |
| -------------------------------------------------------- | -------------------------------------------------------- |
| `System.out.println("Ahoj");`                            | `Console.WriteLine("Ahoj");`                             |
| `Scanner sc = new Scanner(System.in); sc.nextLine();`    | `string? s = Console.ReadLine();`                        |
| `Integer.parseInt(s)`                                    | `int.Parse(s)` / bezpečně `int.TryParse(s, out var x)`   |
| `Random rng = new Random(); rng.nextInt(1,7)` (7 excl.?) | `var rng = new Random(); rng.Next(1, 7)` *(7 excl.)*     |
| `boolean` / `String`                                     | `bool` / `string`                                        |
| `public static void main(String[] args)`                 | `static void Main(string[] args)` *(u klasické šablony)* |
| `Math.sqrt, Math.pow`                                    | `Math.Sqrt, Math.Pow`                                    |
| `equals` u řetězců                                       | `==` porovnává obsah řetězce                             |
| Importy: `import ...`                                    | `using ...;`                                             |

# Otázky na závěr - C# základy a konzole

1. Jaký je rozdíl mezi `Console.Write()` a `Console.WriteLine()`?

2. Co vrací metoda `Console.ReadLine()` a proč je důležité vědět, že jde o text?

3. Proč nemůžeme hodnotu z `Console.ReadLine()` rovnou uložit do proměnné typu `int`?

4. K čemu slouží `int.Parse()` a kdy může jeho použití způsobit problém?

5. Jaký je hlavní rozdíl mezi `Parse()` a `TryParse()`?

6. Co nám říká návratová hodnota `true` nebo `false` u `TryParse()`?

7. Co znamená `out int cislo` v zápisu:

   ```csharp
   int.TryParse(vstup, out int cislo);
   ```

8. Co znamená znak `$` před textovým řetězcem, například:

   ```csharp
   $"Ahoj {jmeno}"
   ```

   a k čemu slouží složené závorky?

9. Jaký je rozdíl mezi datovými typy `int`, `double`, `bool`, `char` a `string`?

10. Co znamenají logické operátory `&&`, `||` a `!` a kdy bychom je využili?

11. Jaký je rozdíl mezi `if`, `else if` a `else`? Kdy se která část podmínky provede?

12. Jaký je rozdíl mezi cykly `while` a `for`? V jaké situaci se více hodí jeden a kdy druhý?

13. Co znamená, že horní hranice u kódu níže je **exkluzivní**? Jaká čísla tedy mohou vzniknout?

   ```csharp
   rng.Next(1, 7)
   ```


14. K čemu slouží metody `Trim()`, `ToLower()` a `ToUpper()` a proč mohou být užitečné při zpracování vstupu od uživatele?

15. Co je metoda? Co jsou její parametry a co znamená návratová hodnota metody?