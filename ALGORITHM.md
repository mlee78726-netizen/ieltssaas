# ALGORITHM.md - Das technische Gehirn

## 🛠️ Modul-Architektur
1. **The Analyzer (STT + LLM)**: Verwandelt Sprache in Text und extrahiert Metriken (Wortschatz-Dichte, Grammatik-Fehler).
2. **The Gap-Finder**: Vergleicht genutzten Wortschatz mit dem angestrebten Band-Niveau und dem passiven Speicher des Nutzers.
3. **The Drill-Generator**: Erstellt on-the-fly Übungen ("Beschreibe X, aber benutze Wort Y").
4. **The Path-Adapter**: Passt den wöchentlichen Lernplan basierend auf der täglichen Performance an.

## 🛡️ Guardrails
- Verwendung von "Chain-of-Thought" Prompts, um Halluzinationen zu minimieren.
- Regelmäßiger Abgleich mit einer kuratierten Datenbank für IELTS-relevante Phrasen.
