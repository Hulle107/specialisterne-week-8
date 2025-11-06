# get_engine()

**Fil:** [utils.py]()<br>
**Linjer:** 22-30<br>

---

![utils.py -> get_engine()](images/utils.get_engine.png)

**Risiko:**

- Passwordet bliver en del af database-URL’en
- Der specificeres ingen kryptering (f.eks. `?ssl=true` eller `connect_args={"ssl": {...}}`)
- Fejl i filadgang eller forbindelse (f.eks. forkert sti, defekte credentials) kaster undtagelser direkte til terminalen

**Konsekvens:**

- Utilsigtet datalæk via logning
- Læk af brugernavne, passwords og data
- Integrity / Observability