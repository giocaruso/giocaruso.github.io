graph TD
    %% ==========================================
    %% STILI DEI BLOCCHI (Colori personalizzati)
    %% ==========================================
    classDef root fill:#004a99,stroke:#002d5d,stroke-width:2px,color:#fff,font-weight:bold;
    classDef core fill:#f8fafc,stroke:#94a3b8,stroke-width:2px,color:#334155;
    classDef page fill:#e0f2fe,stroke:#0284c7,stroke-width:2px,color:#0c4a6e;
    classDef tool fill:#fee2e2,stroke:#dc2626,stroke-width:2px,color:#7f1d1d;
    classDef data fill:#fef08a,stroke:#ca8a04,stroke-width:2px,color:#854d0e;
    classDef external fill:#f3f4f6,stroke:#9ca3af,stroke-width:2px,stroke-dasharray: 5 5;

    %% ==========================================
    %% 1. IL MOTORE CENTRALE (Root)
    %% ==========================================
    Hub["🏠 index.html<br>(Cuore dell'Officina)"]:::root
    CSS["🎨 style.css<br>(Grafica Globale)"]:::core
    JS["⚙️ script.js<br>(Motore Single-Page)"]:::core
    Privacy["📄 privacy.html<br>(Pagina Autonoma)"]:::core

    %% I componenti iniettati da script.js
    Header["🗂️ header.html<br>(Menu Navigazione)"]:::core
    Footer["🗂️ footer.html<br>(Piè di pagina)"]:::core

    %% Collegamenti del Motore
    Hub -. "Carica" .-> CSS
    Hub -. "Carica" .-> JS
    JS -. "Inietta" .-> Header
    JS -. "Inietta" .-> Footer
    Footer --> Privacy

    %% ==========================================
    %% 2. PAGINE DEI CONTENUTI (Cartella /pagine)
    %% ==========================================
    subgraph Contenuti [Pagine Interne Caricate Dinamicamente]
        ChiSono["👤 pagine/chi-sono.html"]:::page
        AreaTest["💻 pagine/area-test.html"]:::page
        Newsletter["📢 pagine/newsletter.html"]:::page
        Prof["🎓 pagine/come-diventare-at.html"]:::page
        CosaFa["⚙️ pagine/cosa-fa-un-tecnico.html"]:::page
        Carriera["📈 pagine/avanzamento-carriera.html"]:::page
        LinkUtili["🌐 pagine/link-utili.html"]:::page
    end

    %% Navigazione dal Menu (Header)
    Header -->|Click| AreaTest
    Header -->|Click| Prof
    Header -->|Click| ChiSono
    Header -. "Torna" .-> Hub

    %% Navigazione dalle Card della Home
    Hub -->|Card| Newsletter
    Hub -->|Card| CosaFa
    Hub -->|Card| Carriera
    Hub -->|Card| LinkUtili
    Hub -->|Card| Prof

    %% ==========================================
    %% 3. AREA SIMULATORI E STRUMENTI
    %% ==========================================
    subgraph Simulatori [Strumenti e Database Quiz]
        CruscottoFuoco["🧯 cruscotto-quiz-antincendio-at.html"]:::tool
        JSON1[("antincendio-lv2-cat.json")]:::data
        JSON2[("quiz-antincendio-lv2-ufficiale-VVF.json")]:::data
    end

    AreaTest -->|Apri| CruscottoFuoco
    CruscottoFuoco -. "Legge Dati" .-> JSON1
    CruscottoFuoco -. "Legge Dati" .-> JSON2

    %% ==========================================
    %% 4. RISORSE ESTERNE
    %% ==========================================
    Appunti["📚 Libri Pubblicati<br>(Link Amazon)"]:::external
    Hub -->|Card Libri| Appunti
    Header -->|Bottone Appunti| Appunti
