graph TD
    Players["4 Local Players"]
    App(("Trivia Wheelhouse\nApplication\n[0]"))
    DB["Embedded SQL\nDatabase"]
    Cache["Local Cache\nFile"]

    Players -- "Name Inputs,\nGame Commands,\nAnswers (A/B/C/D)" --> App
    App -- "Wheel Animations,\nTrivia Text, Timer,\nScoreboard UI" --> Players

    App -- "SQL Queries,\nUsed Question IDs" --> DB
    DB -- "Trivia Data Payloads\n(Questions, Answers, IDs)" --> App

    App -- "Active Session State\n(Scores, Turn Sequence)" --> Cache
    Cache -- "Previous Session State\n(On Crash Recovery)" --> App
