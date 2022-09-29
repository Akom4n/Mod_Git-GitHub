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

    git reset: volta para o estado que estava antes do stage(Removendo da area de stage)

    Git diff:
        Comando que mostra a diferença entre arquivos modificados //Dica: utilizar o VS Code, que mostra graficamente as diferenças. 
    
    Git checkout:
        Permite modificar temporariamente os arquivos do projeto ao estado de um dado commit ou branch

        Código do commit, HEAD
            Cada commit possui um código, que pode ser utilizado para referenciar o commit
            O último commit do histórico do branch corrente também pode ser referenciado pela palavra HEAD
            É possivel referenciar um commit N versões antes de HEAD usando ~N, por exemplo:
                HEAD~1 (penúltimo commit)
                HEAD~2 (antepenúltimo commit)
        
        IMPORTANTE: antes de fazer o checkout para voltar para HEAD, certifique-se que não haja mudanças nos arquivos. Se você acidentalmente mudou alguma coisa, desfaça as modificações usando:
            git reset
            git clean -df
            git checkout -- .

    Como desfazer o último commit:
        Desfazer o último commit sem desgazer as modificações nos arquivos:

            git status
            git reset --soft HEAD~1

    Como deletar commits e também modificações nos arquivos:

        Voltar o projeto ao estado de um dado commit (deletar commits e alterações posteriores a essse commit)

            git status
            git reset --hard <código do commit>

        Voltar o projeto ao estado do penúltimo commit:

            git status
            git reset --hard HEAD~1 

            //ATENÇÃO: Ação destrutiva!
    
    Como atualizar o repositório local em relação ao remoto:

        git status
        git pull <nome do remote> <nome do branch>
    
    Como resolver push rejeitado:

        Não é permitido enviar um push se seu repositório local está atrasado em relação ao histórico do repositório remoto! Por exemplo:

            No GitHub: e8aab78 > 38k2ane > c9g57ef

            No seu computador: e8aab78 > 38k2ane > c9g57ef > a47gc29 > 33p8724

        Você tem que atualizar o repositório local:
            git pull <nome do remote> <nome do branch>

    Como sobrescrever um histórico no GitHub:

        git push -f <nome do remote> <nome do branch> //Ação destrutiva   
        
SOBRE .GITIGNORE:

    É um arquivo que indica o que não deve ser salvo pelo Git

    Geralmente o arquivo .gitignore fica salvo na pasta principal do repositório. Mas também é possível salvar outros arquivos .gitignore em subpastas do repositório, para indicar o que deve ser ignorado por cada subpasta.

    CASOS COMUNS DE ARQUIVOS QUE NÃO DEVEM SER SALVOS PELA GIT:

        Arquivos compilados: Linguagens compiladas (C, C++, JAVA, C#, etc.) geram arquivos de código compilado para executar o programa localmente.

    ARQUIVOS DE BIBLIOTECAS EXTERNAS USADAS NO PROJETO:
       
        Projetos reais utilizam bibliotecas externas (programas prontos disponíveis na internet). Por exemplo, projetos JavaScript com NPM tipicamente salvam uma subpasta "node_modules" na pasta do seu projeto.
    
    ARQUIVOS DE CONFIGURAÇÃO DA SUA IDE

        IDE's podem salvar uma subpasta com arquivos de configuração na pasta do projeto (Exemplo: .vscode).

    ARQUIVOS DE CONFIGURAÇÃO DO SEU SISTEMAS

        Por exemplo, sistemas Mac podem gravar uma subpasta .ds_store na pasta do projeto

O QUE FAZER QUANDO ABRE O EDITOR VIM:

    Estas ações podem abrir o editor VIM no terminal:
        Fazer um commit sem mensagem 
        Fazer um merge de três vias

    Habilitar o modo de edição: i

    Sair do VIM, salvando as alterações: <ESC> :wq <ENTER>

    Sair do VIM, descartando as alterações: <ESC> :q! <ENTER>

COMO APONTAR O PROJETO PARA OUTRO REPOSITÓRIO REMOTO

    git remote set-url origin git@github.com:seuusuario/seurepositorio.git

    Para verificar o remote: git remote -v
    

