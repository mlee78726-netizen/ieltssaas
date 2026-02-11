# MVP_DEFINITION.md - Das absolute Minimum

## 🛠️ Der Fokus
Wir konzentrieren uns im MVP ausschließlich auf **IELTS Speaking Part 1**. Das Ziel ist es, in 5-10 Minuten pro Tag einen messbaren Fortschritt beim aktiven Wortschatz zu erzielen.

## 🚀 Die 3 Kern-Features
1. **The Assessment Engine**: 
   - Ein kurzes Gespräch (3-5 Fragen) zu den Themen: **Home**, **Work/Studies**, **Hobbies**.
   - Die KI transkribiert das Audio und identifiziert genutzte vs. vermiedene Wörter.
2. **The "Passive-to-Active" Tracker**:
   - Eine einfache Liste von "Target Words" für jedes Thema (z.B. Band 8+ Vokabular).
   - System markiert Wörter als "Passiv" (wenn du sie verstehst/liest) und "Aktiv" (wenn du sie korrekt ausgesprochen hast).
3. **The Forced Drill**:
   - Die KI generiert eine neue Frage und gibt dir 2 Wörter vor, die du zwingend einbauen musst.
   - Sofortige Rückmeldung: "Wort X erfolgreich eingebaut, aber die Aussprache von Y war unklar."

## 📱 User Flow (Der tägliche Ablauf)
1. **Start**: Nutzer wählt ein Thema (z.B. Hobbies).
2. **Speaking**: Nutzer beantwortet eine Test-Frage per Sprachnachricht.
3. **Analysis**: KI zeigt: "Du hast 'like' benutzt. Versuch beim nächsten Mal 'be passionate about' oder 'indulge in'."
4. **The Drill**: KI fordert: "Beantworte die Frage nochmal, aber benutze 'indulge in'."
5. **Progress**: Das Wort 'indulge in' rückt einen Punkt näher an den Status "Aktiv".

## 🏗️ Technischer Rahmen
- **Interface**: Ein einfacher Telegram-Bot (unser Prototyp) oder eine Web-App mit Record-Button.
- **Gehirn**: Gemini 3 Flash zur Analyse und Drill-Generierung.
- **Speicher**: Eine JSON-Datei pro Nutzer mit dem Wortschatz-Status.

---
*Status: MVP definiert.*
*Nächster Schritt: Erstellung der Wortschatz-Listen für die 3 Themen.*
