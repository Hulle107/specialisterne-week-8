# load_to_sql()

**Fil:** [utils.py]()<br>
**Linjer:** 160-234<br>

---

![utils.py -> load_to_sql() -> df.to_sql()](images/utils.load_to_sql.connection.png)

**Risiko:**

- Tabellen overskrives (`if_exists="replace"`) uden bekræftelse

**Konsekvens:**

- Tab af data / manglende transaktionskontrol

---

![utils.py -> load_to_sql() -> unique_constraints](images/utils.load_to_sql.constraints.png)

**Risiko:**

- Indsættes af dynamiske SQL-strenge (f.eks. f-strings eller string-concatenation), kan det give risiko for SQL-injection

**Konsekvens:**

- SQL-injection

---

![utils.py -> load_to_sql() -> primary_key](images/utils.load_to_sql.primary.png)

**Risiko:**

- Indsættes af dynamiske SQL-strenge (f.eks. f-strings eller string-concatenation), kan det give risiko for SQL-injection

**Konsekvens:**

- Primærnøgle-definitioner gennem fejlmeddelelser

---

![utils.py -> load_to_sql() -> foreign_keys](images/utils.load_to_sql.foreign.png)

**Risiko:**

- Indsættes af dynamiske SQL-strenge (f.eks. f-strings eller string-concatenation), kan det give risiko for SQL-injection
- `on_delete` og `on_update` er direkte tekst, der kan indeholde vilkårlige SQL-kommandostrukturer

**Konsekvens:**

- SQL-injection via fremmednøgle-definitioner

---

![utils.py -> load_to_sql() -> print](images/utils.load_to_sql.output.png)

**Risiko:**

- Indsættes af dynamiske SQL-strenge (f.eks. f-strings eller string-concatenation), kan det give risiko for SQL-injection
- Output (antal rækker) udskrives direkte til konsollen uden logkontrol

**Konsekvens:**

- Informationslækage / skemadetaljer