sequenceDiagram
    participant Dev as Desenvolvedor
    participant Git as Git Local
    participant GH as GitHub (Servidor)
    participant Repo as Repositório Remoto

    Dev->>Git: git add .
    Dev->>Git: git commit -m "mensagem"
    Dev->>Git: git push origin main

    Git->>GH: Autenticação (token/SSH)
    GH-->>Git: Autorização OK

    Git->>Repo: Envia commits
    Repo-->>GH: Atualiza histórico

    GH-->>Dev: Confirmação de push
