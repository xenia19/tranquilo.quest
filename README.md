graph TB
    subgraph Client["🖥️ Client (PWA)"]
        direction TB
        App["React + Tailwind CSS"]
        SW["Service Worker<br/>(Offline Cache)"]
        
        subgraph Engines["🎮 10 Game Engines"]
            E1["📖 Stories<br/><i>Visual cards + quizzes</i>"]
            E2["🔀 Sorter<br/><i>Swipe categorization</i>"]
            E3["⚡ Chaos<br/><i>Timed reactions</i>"]
            E4["⚔️ Battle<br/><i>Progressive quizzes</i>"]
            E5["🎧 Reels<br/><i>Audio comprehension</i>"]
            E6["🎭 Roleplay<br/><i>AI dialog simulator</i>"]
            E7["📄 PuzzleDoc<br/><i>Document analysis</i>"]
            E8["📞 Call<br/><i>Boss-level challenge</i>"]
            E9["📸 IRL Quest<br/><i>Real-world tasks</i>"]
            E10["🎬 Scene<br/><i>Narrative bridges</i>"]
        end
        
        subgraph GameLayer["🏆 Gamification Layer"]
            XP["XP & Levels"]
            Coins["Coins & Rewards"]
            Achieve["Achievements"]
        end

        subgraph Narrative["📚 Narrative System"]
            NPCs["NPCs: Paco ☕ Antonio 👨‍💻 Carmen 👵"]
            Story["Story Progression"]
        end
    end

    subgraph Firebase["☁️ Firebase"]
        Auth["🔐 Auth"]
        Firestore["📊 Firestore<br/><i>User progress, state,<br/>lesson data</i>"]
    end

    subgraph AI["🤖 AI Services"]
        DeepSeek["DeepSeek AI<br/><i>Text analysis,<br/>error correction,<br/>hints generation</i>"]
        ElevenLabs["ElevenLabs<br/><i>Voice synthesis<br/>(native speaker audio)</i>"]
        Vision["AI Vision<br/><i>Photo verification<br/>for IRL Quests</i>"]
    end

    App --> SW
    App --> Engines
    App --> GameLayer
    App --> Narrative
    
    E6 -->|"Free-text answers"| DeepSeek
    E8 -->|"Dialog responses"| DeepSeek
    E9 -->|"Photo upload"| Vision
    E5 -->|"Audio generation"| ElevenLabs
    E1 -->|"Audio for cards"| ElevenLabs
    
    App -->|"Auth & data"| Firebase
    GameLayer -->|"Save progress"| Firestore
    Narrative -->|"Track state"| Firestore

    style Client fill:#f0f4ff,stroke:#6366f1,stroke-width:2px
    style Firebase fill:#fff7ed,stroke:#f59e0b,stroke-width:2px
    style AI fill:#f0fdf4,stroke:#22c55e,stroke-width:2px
    style Engines fill:#faf5ff,stroke:#a855f7,stroke-width:2px
