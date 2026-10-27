erDiagram
    
    CLUBE ||--o{ INSCRICAO : realiza
    ATLETA ||--o{ INSCRICAO : possui
    COMPETICAO ||--o{ INSCRICAO : recebe
    CATEGORIA ||--o{ INSCRICAO : classifica
    PROVA ||--o{ INSCRICAO : contempla
    INSCRICAO ||--o{ RESULTADO : gera
    ETAPA ||--o{ RESULTADO : registra

    CLUBE {
        int id_clube PK
        string nome_clube
        string sigla
        string uf
    }

    ATLETA {
        int id_atleta PK
        string registro_federativo
        string nome
        date data_nascimento
        string sexo
    }

    COMPETICAO {
        int id_competicao PK
        string nome
        int edicao
        int ano
        date data_inicio
        date data_fim
    }

    CATEGORIA {
        int id_categoria PK
        string nome
        int idade_minima
        int idade_maxima
    }

    PROVA {
        int id_prova PK
        int numero_prova
        int distancia_m
        string estilo
        string sexo
        string tipo_prova
    }

    INSCRICAO {
        int id_inscricao PK
        int id_atleta FK
        int id_clube FK
        int id_competicao FK
        int id_categoria FK
        int id_prova FK
        string status
    }

    ETAPA {
        int id_etapa PK
        int id_competicao FK
        int numero_etapa
        date data
        string turno
    }

    RESULTADO {
        int id_resultado PK
        int id_inscricao FK
        int id_etapa FK
        string tempo
        int colocacao
        decimal pontos
        decimal indice_tecnico
        string status_resultado
    }

#Em caso de problemas, para melhor visualização, segue o link da tabela no MERMAID: https://mermaid.ai/app/projects/86fee403-71d5-43a3-a98f-e5cfba6824c8/diagrams/dedb4c42-407c-47ef-9e95-f5b026f40597/share/invite/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJkb2N1bWVudElEIjoiZGVkYjRjNDItNDA3Yy00N2VmLTllOTUtZjViMDI2ZjQwNTk3IiwiYWNjZXNzIjoiVmlldyIsInB1cnBvc2UiOiJzaGFyZS1pbnZpdGUiLCJpYXQiOjE3OTMwNjUzMzEsImV4cCI6MTc5NTY1NzMzMX0.H_jC6ZUeL52BOdtMJ2gA4b0HTE0M3UwAPdstrA6dgec?entryPoint=share-modal
