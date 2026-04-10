# Mappa del Sito - Officina AT

```mermaid
graph LR
    %% Nodo Principale
    Root["📂 giocaruso.github.io (Root)"]

    %% File di base nella root
    Root --> Index["📄 index.html (Home Page)"]
    Root --> Style["📄 style.css (Grafica)"]
    Root --> Script["📄 script.js (Motore)"]

    %% Cartella Immagini
    Root --> ImgFolder["📁 img"]
    ImgFolder --> Img1["assistente-tecnico-collage.jpg"]
    ImgFolder --> Img2["assistente-tecnico.jpg"]
    ImgFolder --> Img3["copertina-200quiz.jpg"]
    ImgFolder --> Img4["copertina-oltre-profilo.jpg"]
    ImgFolder --> Img5["copertina-tutti-possono.jpg"]

    %% Cartella JSON (Database)
    Root --> JsonFolder["📁 json"]
    JsonFolder --> Json1["🗃️ antincendio-lv2-cat.json"]
    JsonFolder --> Json2["🗃️ quiz-antincendio-lv2-ufficiale-VVF.json"]
    JsonFolder --> Json3["🗃️ quiz-at-200.json"]

    %% Cartella Pagine (Cassetti e componenti)
    Root --> PagineFolder["📁 pagine"]

    %% Pagine base e componenti
    PagineFolder --> Header["📄 header.html"]
    PagineFolder --> Footer["📄 footer.html"]
    PagineFolder --> Privacy["📄 privacy.html"]
    PagineFolder --> ChiSono["📄 chi-sono.html"]
    PagineFolder --> Newsletter["📄 newsletter.html"]

    %% Sezione: Area Test e Simulatori
    PagineFolder --> AreaTestGroup["🛠️ AREA TEST E SIMULATORI"]
    AreaTestGroup --> AreaTestMain["📄 area-test.html"]
    AreaTestMain --> Manuale3["📄 manuale-3-quiz-at.html"]
    Manuale3 --> CruscottoM3["📄 cruscotto-quiz-manuale-3.html"]
    AreaTestMain --> CruscottoAnti["📄 cruscotto-quiz-antincendio-at.html"]
    AreaTestGroup --> MotoreQuiz["📄 motore-universale-quiz.html"]

    %% Sezione: La Professione
    PagineFolder --> ProfessioneGroup["💼 LA PROFESSIONE"]
    ProfessioneGroup --> ComeDiventare["📄 come-diventare-at.html"]
    ProfessioneGroup --> CosaFa["📄 cosa-fa-un-tecnico.html"]
    ProfessioneGroup --> Carriera["📄 avanzamento-carriera.html"]
    ProfessioneGroup --> LinkUtili["📄 link-utili.html"]

    %% Stili personalizzati per dare colore e ordine ai blocchi
    style Root fill:#0052cc,stroke:#000,stroke-width:2px,color:#fff
    style ImgFolder fill:#f9a825,stroke:#000,stroke-width:1px,color:#000
    style JsonFolder fill:#f9a825,stroke:#000,stroke-width:1px,color:#000
    style PagineFolder fill:#f9a825,stroke:#000,stroke-width:1px,color:#000
    style AreaTestGroup fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
    style ProfessioneGroup fill:#e3f2fd,stroke:#1565c0,stroke-width:2px