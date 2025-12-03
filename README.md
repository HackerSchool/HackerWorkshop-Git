# 🕵 Git Resistance: O Jogo

Damos-te as boas vindas ao teu primeiro HackerWorkshop do teu estágio: **Workshop de Git**! O objetivo é jogar *The Resistence* enquanto aprendes git. Se nunca jogaste *The Resistence*, podes encontrar as regras [aqui](https://cdn.1j1ju.com/medias/1e/da/43-the-resistance-rulebook.pdf), mas a ideia geral do jogo é aprovar 3 missões com sucesso enquanto que os x-biters vão tentar sabotar 3 missões sem serem descobertos.

## 📂 Estrutura do Repositório

  * presencas.md (Ficheiro vazio, será preenchido por todos no final do jogo).

  * missao_01/ ➝ contém equipa_atual.md

  * missao_02/ ➝ contém equipa_atual.md

  * missao_03/ ... (até à missão 5)

## 🎭 Descobrir a Tua Identidade

**Por padrão, todos os estagiários são HACKERS (Resistência).**

Apenas os x-biters (impostores) recebem uma mensagem privada no Discord antes do jogo começar.

**Antes de começares a jogar, confirma se não recebeste mensagem privada no Discord:**

![Ver dm's no discord](discord_message.jpg "Ver mensagens privadas no Discord")

-----

## 🔄 O Ciclo de Jogo (Por Ronda)

### 1. A Liderança 👑

  * Toda a gente se reúne em círculo.

  * Um objeto físico (o "Token de Líder") passa de mão em mão para definir o Líder da ronda atual.

### 2. A Escolha da Equipa (Branch & PR) 🤝

  * A pessoa escolhida como Líder cria uma nova branch localmente (ex: equipa-ronda-1).

  * Edita o ficheiro missao_X/equipa_atual.md e escreve os nomes d@s estagiári@s que quer levar para a missão.

  * Faz *Commit* e *Push*.

  * Abre um *Pull Request (PR)* para a main.

### 3. A Votação Pública (Code Review) 🗳

  * Tod@s vão ao GitHub ver o PR.

  * *Aprovar a Equipa:* Selecionar "Approve" (Review changes).

  * *Rejeitar a Equipa:* Selecionar "Request Changes".

  * *Contagem:* O Game Master verifica o PR.

      * Maioria Rejeita: A pessoa Líder fecha o PR. O Token passa para a próxima pessoa.

      * Maioria Aprova: O Game Master faz *Merge* do PR para a main. A missão avança!

### 4. A Missão (Push Anónimo) 🕵‍♂

  * *Apenas* os membros listados no equipa_atual.md jogam nesta fase.

  * Os membros da equipa fazem git pull.

  * *Configuração de Anonimato (OBRIGATÓRIO):*

    Devem correr estes comandos na consola para não serem identificados no histórico:

    *Se fores x-biter (impostor):*
    ```bash
    git config --local user.name "xb"
    git config --local user.email "xad0w.b1ts@stt.pt"
    ```

    *Se fores hacker (bom):*
    ```bash
    git config --local user.name "hacker"
    git config --local user.email "hacker@hackerschool.pt"
    ```

  * *A Ação:*

    Criam um ficheiro novo dentro da pasta da missão com um nome aleatório (ex: voto_a8j2k.md ou voto_19283.md) para evitar conflitos.

  * *O Voto:*

    Dentro desse ficheiro escrevem apenas uma palavra:

      * SUCESSO (Resistência deve votar sempre isto; x-biters podem votar isto para disfarçar).

      * FALHA (Apenas x-biters podem votar isto).

  * *Envio:*

    Fazem git add, git commit e git push.

### 5. O Resultado 📉

  * O Game Master faz git pull na main.

  * Abre a pasta da missão e verifica os ficheiros de voto.

  * Anuncia se a missão teve Sucesso (0 falhas\*) ou se Falhou (1 ou mais falhas).

      * (Nota: Na missão 4, são precisas 2 falhas, dependendo se nº de jogadores > 7).

-----

## 🏁 Fim do Jogo & Cleanup

Assim que uma equipa chegar às 3 vitórias:

1.  O jogo termina.

2.  *Exercício Final (Conflitos):* Todos os estagiários devem, ao mesmo tempo, editar o ficheiro presencas.md na raiz, colocar o seu nome real e fazer push.

-----

### 💡 Dicas para o Game Master

  * Garante que ninguém faz git pull durante as missões até todos terem votado, para não verem os votos a chegar um a um.

  * Se alguém se esquecer de mudar o git config, o commit vai aparecer com o nome e foto verdadeiros no GitHub. É "Game Over" para essas pessoas, então é melhor se calhar fazer uns testes antes.


## About Git: 
![](speed_run_git.png)

### 🚑 Quick Troubleshoot (SOS)

**"Instalei o Git mas o comando não funciona!"**

  * 👉 Reinicia o terminal (fecha e volta a abrir).

**"O Git está a gritar comigo a perguntar quem sou!"**

  * 👉 Tens de configurar a tua identidade (só uma vez):

    ```bash
    git config --global user.name "O Teu Nome"
    git config --global user.email "teu@email.com"
    ```

**"Tento fazer push e dá erro!"**

  * 👉 Provavelmente alguém fez alterações no GitHub que tu não tens. Faz primeiro `git pull` (traz as novidades) e depois tenta de novo.
