# _read_credentials()

**Fil:** [utils.py]()<br>
**Linjer:** 22-30<br>

---

![utils.py -> _read_credentials()](images/utils._read_credentials.png)

**Risiko:**

- Projektet gemmer database-login i klartekst i filen `credentials_file.txt`.

**Konsekvens:**

- Uautoriseret adgang til databasen og datatab.