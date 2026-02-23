# AI Integration Assignment — Car Rental Customer Request Router

## 🎯 Cieľ

Cieľom zadania je ukázať, ako navrhuješ a implementuješ integračné workflow s využitím AI v reálnom scenári.

Nejde o dokonalý produkt, ale o:

* spôsob uvažovania,
* robustnosť návrhu,
* prácu s chybami,
* praktické použitie AI.

---

## 🏢 Kontext

Požičovňa áut dostáva požiadavky od zákazníkov cez rôzne kanály (email, formulár, support ticket).

Obsah požiadaviek je neštruktúrovaný text a je potrebné ich automaticky spracovať a smerovať.

---

## 🧩 Zadanie

Navrhni workflow v nástroji podľa vlastného výberu (napr. n8n, Make, vlastné riešenie), ktorý bude fungovať ako:

👉 **AI Customer Request Router**

---

## 1️⃣ Vstup požiadavky

Workflow musí vedieť prijať požiadavku cez webhook.

Príklad payload:

```json
{
  "message": "Hi, I want to extend my booking by 2 days",
  "customerId": "123",
  "bookingId": "B-456"
}
```

Validuj vstup:

* musí existovať `message`
* ak chýba → error flow

---

## 2️⃣ AI klasifikácia

Použi AI (alebo mock), aby si klasifikoval typ požiadavky:

* EXTENSION
* CANCELLATION
* DAMAGE_REPORT
* PRICE_INQUIRY
* OTHER

### Dôležité

Môžeš použiť:

* vlastný AI API kľúč,
* iný LLM,
* lokálny model,
* alebo mock riešenie.

👉 Nehodnotíme kvalitu modelu, ale návrh workflow.

---

## 3️⃣ Rozhodovanie

Podľa kategórie sprav akciu:

### EXTENSION

* zapíš do logu požiadaviek
* pošli notifikáciu operátorovi

### CANCELLATION

* označ ako štandardná požiadavka
* zapíš do logu

### DAMAGE_REPORT

* označ ako high priority
* pošli alert

### PRICE_INQUIRY

* priprav automatickú odpoveď

### OTHER

* fallback queue

---

## 4️⃣ Logging

Ulož minimálne:

* pôvodnú správu
* klasifikáciu
* timestamp

Môžeš použiť:

* súbor,
* databázu,
* Google Sheet,
* alebo mock endpoint.

---

## 5️⃣ Error handling

Workflow musí obsahovať:

* fallback ak AI zlyhá
* validáciu vstupu
* error branch

---

## 📦 Odovzdanie

Prosíme o:

* export workflow (napr. n8n JSON),
* krátky README:

Popíš:

* prečo si workflow navrhol takto,
* kde sú riziká,
* čo by si zmenil v produkcii,
* ako by si riešil správu API kľúčov.

---

## ⭐ Bonus (nepovinné)

Navrhni:

👉 ako by systém vedel navrhnúť alternatívne auto ak zákazník žiada predĺženie a vozidlo nie je dostupné.

---

## 🧠 Na čo sa pozeráme

* jednoduchosť workflow,
* jasná logika,
* práca s chybami,
* rozumné použitie AI,
* praktické myslenie.

---

## ⚠️ Poznámka

Workflow nemusí byť plne produkčný — dôležitý je návrh a rozhodnutia.

---

## 💬 Follow-up

Po odovzdaní v prípade, že sa nám tvoje riešenie páči, si dáme krátky rozhovor (10–15 min), kde prejdeme tvoje riešenie.
