# Fluxo de Trabalho com Git e GitHub

## Introdução

Este documento descreve o processo que seguiremos para trabalhar de forma colaborativa no projeto de reforma do site. Vamos utilizar **Git** para o controle de versões do código e **GitHub** para revisar e aprovar as alterações antes de adicioná-las à versão final.

## O que é Git e GitHub?

-   **Git** é uma ferramenta que ajuda a rastrear todas as mudanças feitas no código. Isso permite que mais de uma pessoa trabalhe no mesmo projeto sem se perder.
-   **GitHub** é uma plataforma online onde podemos armazenar e compartilhar nosso código usando Git. Ele também nos ajuda a revisar o código dos colegas e garantir que tudo esteja correto antes de lançar no site.

## 1. Instalação do Git

Antes de começar, você precisa instalar o Git no seu computador.

### Windows

1. Baixe o Git no site oficial: [https://git-scm.com/downloads](https://git-scm.com/downloads)
2. Instale o Git usando o assistente de instalação. Pode manter as opções padrão.

### Linux

1. No terminal, execute:
    ```bash
    sudo apt-get update
    sudo apt-get install git
    ```

### macOS

1. Se você tiver o Homebrew instalado, execute:
    ```bash
    brew install git
    ```

Para verificar se a instalação foi bem-sucedida, abra o terminal (ou cmd no Windows) e digite:

```bash
git --version
```

Se o Git estiver instalado corretamente, ele retornará a versão instalada.

## 2. Clonar o Repositório

Agora que o Git está instalado, você precisa "clonar" o repositório do projeto no GitHub para o seu computador. Isso vai baixar o código que já existe no projeto.

1. No terminal (ou cmd), execute o comando abaixo, substituindo `URL_DO_REPOSITORIO` pela URL do repositório no GitHub:

    ```bash
    git clone URL_DO_REPOSITORIO
    ```

2. Entre na pasta do projeto:
    ```bash
    cd nome-do-repositorio
    ```

Agora você já tem o código do projeto no seu computador!

## 3. Criar uma Nova Branch

Vamos usar um sistema de **branches**. Pense nas branches como cópias separadas do projeto. Sempre que você for trabalhar em uma nova funcionalidade ou correção, crie uma nova branch. Isso evita que mudanças não testadas vão direto para a versão principal.

1. Antes de criar uma nova branch, garanta que você está na branch `dev`:

    ```bash
    git checkout dev
    ```

2. Atualize a branch `dev` com a versão mais recente do código:

    ```bash
    git pull origin dev
    ```

3. Agora, crie uma nova branch para sua tarefa (ex.: corrigir o menu do site):
    ```bash
    git checkout -b feature/menu-correção
    ```

> Por que isso é importante? Cada branch é um "isolamento" onde você pode fazer suas alterações sem afetar o código principal. Isso evita que o código quebrado ou incompleto entre na versão final.

## 4. Fazer Alterações e Commitar

Agora que você está em sua branch, você pode fazer suas alterações no código. Após fazer as alterações, precisamos "commitar" essas mudanças.

1. Verifique os arquivos que você alterou:

    ```bash
    git status
    ```

2. Adicione os arquivos alterados ao commit:

    ```bash
    git add .
    ```

3. Crie um commit com uma mensagem explicando o que foi feito:
    ```bash
    git commit -m "Corrige o menu do site para funcionar em dispositivos móveis"
    ```

> Por que isso é importante? O commit cria um "ponto de restauração" no seu código. Se algo der errado, podemos voltar para o estado anterior facilmente.

## 5. Enviar a Branch para o GitHub

Após commitar suas mudanças, envie sua branch para o repositório no GitHub. Isso nos permite ver suas alterações e revisar o código.

1. Envie sua branch para o GitHub:

    ```bash
    git push origin nome-da-sua-branch
    ```

2. Vá até o repositório no GitHub e crie um **Pull Request (PR)**. Isso vai pedir para que o código da sua branch seja revisado e, se aprovado, mesclado na branch `dev`.

### Como criar um Pull Request:

1. No GitHub, vá até a aba **Pull Requests** e clique em **New Pull Request**.
2. Escolha `dev` como a branch de destino e a sua branch como origem.
3. Escreva uma descrição clara das alterações feitas.
4. Atribua revisores para revisar o código.
5. Clique em **Create Pull Request**.

> Por que isso é importante? O Pull Request nos permite revisar o código antes que ele vá para a branch de desenvolvimento. Isso garante que não haja erros e que todos no time concordem com as mudanças.

## 6. Revisão de Código (Code Review)

Depois de criar o Pull Request, os revisores vão olhar o código e garantir que tudo está funcionando corretamente.

### O que pode acontecer:

-   **Aprovação**: Se estiver tudo certo, a PR será aprovada e sua branch será mesclada na `dev`.
-   **Solicitação de Mudanças**: Se algo precisa ser ajustado, o revisor fará comentários e você poderá corrigir o código e atualizar a PR.

> Por que isso é importante? Revisar o código antes de mesclá-lo é uma boa prática que evita bugs e melhora a qualidade do projeto.

## 7. Mesclar para Produção

Quando o código na `dev` estiver estável e pronto para produção, faremos uma **Pull Request** da branch `dev` para a branch `main`. Após revisão final, o código será mesclado na `main`, e essa versão estará pronta para ser lançada em produção.

> Por que isso é importante? A branch `main` é a versão que vai para produção, ou seja, o código que estará no site. Devemos garantir que apenas código funcional e estável chegue à produção.

## Resumo do Fluxo de Trabalho

1. **Clonar o repositório** no seu computador.
2. **Criar uma nova branch** a partir de `dev` para trabalhar em sua tarefa.
3. **Fazer as alterações** e commitar seu código.
4. **Enviar sua branch** para o GitHub e criar um Pull Request.
5. **Revisar e aprovar** o Pull Request.
6. **Mesclar o código** na branch `dev` (ou `main` quando for para produção).

Esse fluxo nos ajuda a organizar o trabalho, evitar erros e garantir que o código esteja sempre estável. Vamos seguir esses passos para garantir que o projeto avance de forma profissional e sem problemas!

## Dúvidas?

Se tiver alguma dúvida em qualquer uma das etapas, é só perguntar!
