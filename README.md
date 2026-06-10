# Storytelling mit KI
### 

---

## API-Schlüssel für KI:connect / RWTHgpt

OpenCode verwendet in diesem Template den Anbieter `kiconnectnrw:rwth` bzw. `kiconnectnrw:fhaachen` aus `./.opencode/opencode.jsonc`. Dafür brauchen Teilnehmende einen persönlichen API-Schlüssel von KI:connect / RWTHgpt.

Die offizielle Anleitung findest du hier:

- [API-Keys und Zugriff (RWTHgpt / KI:connect)](https://help.itc.rwth-aachen.de/service/1808737e10424937b76e564ed15d8028/article/4f07ebbbc8c4477a8db9baa441494941/)

Kurzfassung der Schritte:

1. Mit RWTH Single Sign-On an der [KI:connect-Weboberfläche](https://chat.kiconnect.nrw/) anmelden.
2. Links unten den eigenen Namen auswählen.
3. Die **API-Schlüsselverwaltung** öffnen.
4. Einen **Schlüssel erstellen** und den persönlichen API-Schlüssel anlegen.
5. Den Platzhalter `__PERSONAL_API_KEY__` in `./.opencode/opencode.jsonc` mit dem eigenen Schlüssel ersetzen.

Der Schlüssel ist vertraulich zu behandeln und darf nicht ins Repository eingecheckt werden.

---

## 🚨 Leitplanken gegen KI-Fehler (Die 5-Punkte-Checkliste)

Wenn du Code von einem Agenten prüfen oder generieren lässt, achte stets auf diese 5 Punkte:
1.  **Erfüllt es die Aufgabe?** (Spec danebenlegen und Punkt für Punkt prüfen)
2.  **Randfälle bedacht?** (Leere Eingaben, Null-Werte, unerwartete Formate)
3.  **Gibt es Sicherheitskonflikte?** (SQL-Injections, hartcodierte Secrets/Passwörter)
4.  **Sind Struktur & Namen lesbar?** (Verständliche Variablennamen, Funktionslängen)
5.  **Wo halluziniert der Code?** (Nicht existierende Bibliotheken, erfundene Parameter)

---

Viel Erfolg und viel Spaß beim Experimentieren im Workshop! 💻✨
