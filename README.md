# Vaksinasjonstriageringsprogram

Dette programmet hjelper helsepersonell med å vurdere **hvilken vaksine en voksen pasient bør tilbys i det norske voksenvaksinasjonsprogrammet**, i tråd med **Folkehelseinstituttets veileder**.  

Formålet er å gjøre beslutningsstøtten enkel og konsistent i klinisk praksis.  

---

## Gjeldende versjon (2025)
- **65-åringer født i 1960** tilbys **pneumokokkvaksine**.  

---

## Fremtidige oppdateringer
Det forventes årlige justeringer i henhold til FHI-veilederen:  
- I **2026** blir det trolig **65-åringer født i 1961** som skal tilbys pneumokokkvaksine.  

👉 **Merk:** Programmet må derfor oppdateres hvert år slik at riktig fødselsårgang fanges opp i logikken.  

---

## Eksempel på kodejustering

Dagens logikk (2025):

```python
if patient.age == 65 and patient.birth_year == 1960:
    recommendation = "Tilby pneumokokkvaksine"
````

Oppdatert logikk for 2026:

```python
if patient.age == 65 and patient.birth_year == 1961:
    recommendation = "Tilby pneumokokkvaksine"
```

For enklere vedlikehold kan fødselsår settes som en variabel:

```python
CURRENT_ELIGIBLE_YEAR = 1960  # Endres til 1961 i 2026

if patient.age == 65 and patient.birth_year == CURRENT_ELIGIBLE_YEAR:
    recommendation = "Tilby pneumokokkvaksine"
```

---

## Kilde

* [Folkehelseinstituttet – Vaksinasjonsveilederen](https://www.fhi.no/tema/vaksiner/)
