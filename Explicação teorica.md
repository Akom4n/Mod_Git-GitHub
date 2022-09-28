Explicação teorica


REPOSITÓRIO LOCAL E REMOTO:

    Um projeto controlado pelo Git é chamado de repositório de versionamento.

    Tipicamente uma cópia "oficial" do repositório fica salvo em um servidor (repositório remoto).

    Cada pessoa que trabalha no projeto pode fazer uma cópia do repositório para seu computador(repositório local). A pessoa então faz suas alterações no projeto (novos commits) e depois salva as alterações no servidor.

    git clone para clonar um repositório remoto quando você não tem ele no computador.
    git pull normalmente usado para trazer as atualizações feitas em outra maquina para o respositório que você já tem no computador.

    commit usado normalmente para atualizar o que foi feito no repositório.

    git push usado normalmente para enviar o que foi feito no repositório local para o remoto.


COMANDOS PARA CONFIGURAR IDENTIFICAÇÃO NO GIT:

    Para testar se está reconhecendo o git é só digitar: git
    Para ver a versão do git: git --version
    Zoom in/ Zoom out: control+, control-
    Para configurar nome: git config --global user.name "Akom4n"
    Para configurar email: git config --global user.email "xdenik13@gmail.com" //usado normalmente o email do github
    Ver o que está configurado: git config --list
    Verificando o histórico de versões: git log / Listagem resumida dos commits: git log --oneline

    

CONFIGURAR CHAVE SSH PARA O GITHUB:

    SSH é um protocolo para comunicação de dados com segurança.

    O GitHub aboliu a autenticação somente com usuário e senha.

    A ideia básica é cadastrar previamente quais computadores podem acessar o GitHub em seu nome. Outros computadores não conseguem acessar.

    Para isto você deve:

    (1) Gerar uma chave SSH no seu computador
    (2) Cadastrar essa chave no seu GitHub

    Para criar a nova chave SSH use:

    ssh-keygen -t ed25519 -C "xdenik13@gmail.com"

    OBS: Se você estiver usando um sistema legado que não é compatível com o algoritmo Ed25519, use: ssh-keygen -t rsa -b 4096 -C "xdenik13@gmail.com"

    Isto cria uma nova chave SSH, usando o nome de e-mail fornecido como uma etiqueta

INICIANDO UM REPOSITORIO PARA O GITHUB DA SUA MAQUINA:

    git init
    git add .
    git commit -m "Mensagem explicativa"
    git branch -M main
    git remote add origin git@github.com:Akom4n/Mod_Git-GitHub.git
    git push -u origin main

COMANDOS PARA O USO DO GIT BASH

    Sobre o Git status/git add e stage:

    modified: Arquivo modificado / untracked: Arquivo novo que você ainda não salvou / deleted: Arquivos que foram deletados

    staged 

    commited

    git reset: volta para o estado que estava antes do stage

    Git diff:
        Comando que mostra a diferença entre arquivos modificados //Dica: utilizar o VS Code, que mostra graficamente as diferenças. 
