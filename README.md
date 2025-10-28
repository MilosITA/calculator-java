# Izveštaj – Statička analiza i LOC metrike

## LOC
Ukupan broj linija koda: **188 linija (134 LOC)**  
Veličina fajla: **5.93 KB**

---

## Statička analiza

| Fajl | Linija | Zapažanje |
|------|---------|------------|
| Calculator.java | 5 | Klasa koristi statičko polje `finalResult`, što nije preporučljivo jer može izazvati probleme sa višedretvenošću. |
| Calculator.java | 9–23 | Unutrašnja klasa `Operations` ima metodu `ToString()` – treba da bude `toString()` u skladu sa Java konvencijom. |
| Calculator.java | 27 | Metoda `Run()` treba da se zove `run()` (Java konvencija). |
| Calculator.java | 32–35 | Nema validacije praznog stringa — može izazvati `StringIndexOutOfBoundsException`. |
| Calculator.java | 67–80 | Hvata se generički `Exception` — preporučuje se korišćenje `NumberFormatException`. |
| Calculator.java | 84–157 | Metoda `Calculate()` je preduga i ponavlja logiku — preporučuje se refaktorisanje u manje metode. |

---

## Preporuke

- Preimenovati metode u skladu sa Java konvencijama (`run`, `toString`, itd).  
- Dodati proveru za prazan ili `null` unos pre obrade izraza.  
- Ukloniti statičko polje `finalResult` i koristiti lokalne promenljive.  
- Refaktorisati metodu `Calculate()` radi smanjenja ponavljanja koda.  
- Dodati JUnit testove umesto oslanjanja na `System.out.println`.  
- Hvatanje specifičnih izuzetaka (`NumberFormatException`, `ArithmeticException`) umesto opšteg `Exception`.

---

## Zaključak

Kod funkcioniše ispravno za osnovne izraze, ali postoje:  
- nedoslednosti u imenovanju metoda,  
- ponavljanje koda,  
- nedostatak validacije korisničkog unosa,  
- i korišćenje statičkih polja bez potrebe.

**Preporuka:** izvršiti refaktorisanje i dodati testove radi bolje održivosti i čitljivosti koda.

---

**Autor izveštaja:** Miloš Tripković  
**Datum:** 28.10.2025  
