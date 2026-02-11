# ALGORITHM.md - Das technische Gehirn (MVP Version)

## 🧠 Der "Forced Output" Kreislauf
Unser Algorithmus arbeitet in einer geschlossenen Schleife, um den Übergang von passiv zu aktiv zu erzwingen.

### Schritt 1: The Scanner (Analyse)
- **Input**: Transkript der Nutzerantwort (via Whisper).
- **Logik**: Das LLM (Gemini 3 Flash) bekommt die Liste der "Target Words" für das Thema.
- **Output**: 
  - `Used`: Wörter, die der Nutzer korrekt eingebaut hat.
  - `Missed`: Wörter, die zum Kontext gepasst hätten, aber durch einfachere Begriffe ersetzt wurden (Avoidance Detection).
  - `Status Update`: Der "Mastery Score" für jedes Wort wird in der Nutzer-JSON aktualisiert.

### Schritt 2: The Gap-Finder (Lücken-Identifikation)
- Das System wählt 2-3 Wörter aus der `Missed`-Liste oder Wörter mit einem niedrigen Mastery-Score aus.
- Priorisierung: Wörter, die für Band 7-9 essentiell sind (z.B. Idiome oder präzise Adjektive).

### Schritt 3: The Drill-Generator (Erzwingung)
- **Prompt-Konstruktion**: "Die letzte Antwort war gut, aber du hast 'like' statt 'passionate about' gesagt. Beantworte die folgende Frage (oder die gleiche nochmal) und baue zwingend 'passionate about' und 'indulge in' ein."
- **Constraint-Check**: Das System validiert nach der Antwort sofort: Wurden die Wörter benutzt? Wurden sie im richtigen grammatikalischen Kontext genutzt?

### Schritt 4: Feedback & Correction
- Kein langes Blabla. Kurze, knackige Korrektur:
  - "Check: 'Indulge in' perfekt genutzt."
  - "Korrektur: 'Passionate about' braucht ein Gerundium (-ing) danach."

## 📊 Datenstruktur (User Profile)
Jeder Nutzer hat ein JSON-Profil:
```json
{
  "topic_hobbies": {
    "passionate_about": { "score": 3, "status": "active" },
    "indulge_in": { "score": 1, "status": "passive" }
  }
}
```
Ein Wort gilt als **Aktiv**, wenn es in 3 aufeinanderfolgenden Sessions in freien Antworten (nicht Drills) korrekt genutzt wurde.

---
*Status: Algorithmus-Logik für Phase 2 dokumentiert.*
