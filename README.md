# Knowledge Bases - ontology
Project carried out as part of the subject in the Knowledge Bases studies

As part of the laboratories, I created my own ontology, which was a formalized model of the world. I learned the principles of creating such models as well as high-level principles of distinguishing and classifying objects, which were also useful in modeling information systems.

## Project Topic
"The Transportation Company and the Transport of a Specific Pallet"

## Project requirements
General requirements for the ontology, I would like to establish the following:

1. At least 10 concepts (including complex concept equivalents).
2. At least 3 roles.
3. An interesting inference method, preferably for presentation to the instructor:
   - Utilizing the concept R some (R some C).
   - Utilizing the concept R only C.
   - Utilizing the concept R min n C.
   - Utilizing the concept R max n C.
   - Utilizing exhaustive inheritance
     (e.g., classes are exclusively divided into lectures, laboratories, seminars, and projects).

## Project environment
`Protege 4.3`

## Project summary (in Polish, because the project was meant to be in Polish)
### Koncepty (min 10):
  1. FirmaTransportowa
  2. Pracownik
  3. Pojazd
  4. Ciezarowka
  5. Samochod
  6. Zamowienie
  7. Paleta
  8. Przewoz
  9. Klient
  10. Adres

### Role (min3):
- Wykorzystując koncept R some (R some C) możemy wywnioskować, że każde zamówienie musi mieć przynajmniej jeden przewóz. Możemy to zapisać następująco:
Zamówienie subClassOf: maPrzewoz some Przewoz
maPrzewoz: D: Zamowienie, R: Przewoz

- Wykorzystując koncept R only C możemy wywnioskować, że każdy klient może mieć tylko jeden adres. Możemy to zapisać następująco:
Klient subClassOf: maAdres only Adres
maAdres: D: Klient or Pracownik, R: Adres

- Wykorzystując koncept R min n C możemy wywnioskować, że każde zamówienie musi mieć co najmniej jedną paletę. Możemy to zapisać następująco:
maPalete: D: Zamowienie, R: Paleta
Zamowienie subClassOf: maPalete min 1 Paleta

- Wykorzystując koncept R max n C możemy wywnioskować, że każdy przewóz może przewieźć co najwyżej jedną paletę. Możemy to zapisać następująco:
przewoziPalete: D: Ciezarowka, R: Paleta
Przewóz subClassOf: przewoziPaletę max 1 Paleta

- Wykorzystując dziedziczenie wyczerpujące, możemy wywnioskować, że każdy pojazd jest albo samochodem, albo ciężarówką. Możemy to zapisać następująco:
Pojazd subClassOf: Samochód or Ciężarówka

- Każda firma ma zamówienia: maZamówienie: D: FirmaTransportowa, R: Zamowienie

- Każda firma ma pojazd: maPojazd: D: FirmaTransportowa, R: Pojazd

- Każda firma transportowa ma co najmniej jednego pracownika:
maPracownika: D: FirmaTransportowa, R: Pracownik,
FirmaTransportowa Equivalent To: maPracownika min 2 Pracownik

### Wnioskowanie:

Na podstawie dostarczonych informacji możemy wyciągnąć następujące wnioski:

1. Firma "Trans Pol" dysponuje minimum 2 samochodami i 2 pracownikami.

2. Każde zamówienie jest powiązane z konkretnym klientem, który ma swój adres.

3. Każde zamówienie składa się z 1 do 2 palet.

4. Każde zlecenie transportowe jest powiązane z konkretnym zleceniem i wymaga minimum 1 pojazdu i 1 pracownika.

5. W skład pojazdów firmy wchodzą zarówno samochody ciężarowe, jak i osobowe.

6. Tylko samochody ciężarowe mogą przewozić palety; samochody nie nadają się do tego celu.

Wnioski te pochodzą z podanych stwierdzeń i odzwierciedlają logiczne relacje między podmiotami i ich właściwościami w dziedzinie transportu.

### Inference:

Based on the provided information, we can make the following inferences:

1. The company "Trans Pol" has a minimum of 2 vehicles and 2 employees. 

2. Each order is associated with a single customer who has their own address.

3. Each order consists of 1 to 2 pallets.

4. Each transportation assignment is linked to a specific order and requires a minimum of 1 vehicle and 1 employee.

5. The company's vehicle fleet includes both trucks and cars.

6. Only trucks are capable of transporting pallets; cars are not suitable for this purpose.

These inferences are derived from the given statements and reflect the logical relationships between the entities and their properties in the transportation domain.

![obraz](https://github.com/AgnieszkaDelmaczynska/knowledge-bases-ontology/assets/105732925/41ed640a-989f-4cc6-af2e-6a24d1fa4dd0)

![obraz](https://github.com/AgnieszkaDelmaczynska/knowledge-bases-ontology/assets/105732925/2dfe13cc-1ba1-4d94-8224-bd7dcd3ebaca)

