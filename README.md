
#Aula de Git & GitHub
---

Até agora, aprendemos sobre os fundamentos do **Versionamento de Código** com **Git** e como o **GitHub** atua como uma plataforma essencial para isso.

---

### Resumo do que aprendemos:

1.  **Versionamento de Código (VCS):**
    * É um sistema para **rastrear e gerenciar mudanças** em arquivos ao longo do tempo.
    * Funciona como uma "máquina do tempo" para o seu código, permitindo **voltar a versões anteriores** se algo der errado.
    * Facilita o **trabalho em equipe**, permitindo que vários desenvolvedores trabalhem no mesmo projeto sem sobrescrever o trabalho uns dos outros.

2.  **Git (Sistema de Controle de Versão Distribuído - DVCS):**
    * É o **VCS distribuído mais popular**.
    * Em um DVCS, cada desenvolvedor tem uma **cópia completa do histórico** do projeto em sua máquina local.
    * Permite **trabalhar offline** e fazer commits (salvar alterações) localmente.
    * Facilita a criação e o gerenciamento de **branches (ramificações)** para desenvolver novas funcionalidades ou corrigir bugs de forma isolada, e depois **mesclar (merge)** essas mudanças de volta ao código principal.

3.  **GitHub (Plataforma de Hospedagem e Colaboração):**
    * É uma **plataforma online** que hospeda repositórios Git.
    * Atua como uma **nuvem para seu código**, fornecendo backup e acesso remoto.
    * Funciona como uma **rede social para desenvolvedores**, permitindo compartilhar projetos, colaborar e construir um portfólio.
    * Oferece **ferramentas de colaboração** como Issues (para rastrear tarefas e bugs) e Pull Requests (para propor e revisar mudanças de código).

4.  **Criando Pastas no Git:**
    * Entendemos que o Git **rastreia arquivos, não pastas vazias**.
    * Para uma pasta ser incluída no repositório, ela precisa conter pelo menos um arquivo (por exemplo, um `.gitkeep` ou um `README.md`).
    * O processo envolve **criar a pasta** no sistema de arquivos, **adicionar um arquivo** dentro dela, e então usar os comandos **`git add`**, **`git commit`** e **`git push`** (se for para um repositório remoto) para que as mudanças sejam registradas.

5.  **Encontrando Pastas no PC:**
    * Vimos como usar as **ferramentas de busca** do sistema operacional (Explorador de Arquivos/Finder/Spotlight) para localizar pastas.
    * Aprendemos a **navegar entre diretórios** usando o comando `cd` no terminal, o que é fundamental para trabalhar com projetos Git.

Em resumo, o Git nos dá o poder de gerenciar as versões do nosso código de forma local e eficiente, enquanto o GitHub potencializa a colaboração e o compartilhamento desses projetos em um ambiente online.

---


## Comandos Git Essenciais

| Comando Git            | O que faz                                              |
| ----------------- | ---------------------------------------------------------------- |
| git init      | inicializa um novo repositório Git em uma pasta local. Ele cria a subpasta .git oculta, que armazena todo o histórico do projeto. |
| git clone [url_do_prjeto]   | 	Cria uma cópia local de um repositório Git já existente (geralmente de uma plataforma como GitHub)|
| git status      | Mostra o estado atual do seu repositório: quais arquivos foram modificados, quais estão prontos para serem "comitados" (na área de staging), e quais não estão sendo rastreados.|
| git add [nome_do_arquivo]     | !Adiciona um arquivo específico à área de staging. Isso significa que o arquivo está pronto para ser incluído no próximo commit. |
| git add . |Adiciona todos os arquivos novos e modificados (na pasta atual e subpastas) à área de staging. |
|git commit -m "[Mensagem do commit]" |Salva as alterações que estão na área de staging no histórico do seu repositório local. A mensagem é crucial para descrever o que foi feito. |
|git log |Exibe o histórico de commits do seu repositório, mostrando quem fez o quê, quando e com qual mensagem. |
|git branch |Lista todas as branches (ramificações) existentes no seu repositório local e indica qual branch você está usando no momento. |
|git branch [nome_da_nova_branch] |Cria uma nova branch com o nome especificado, baseada na branch atual.|
|git checkout [nome_da_branch] ou git switch [nome_da_branch] |Muda para uma branch existente. O git switch é o comando mais moderno para essa função.|
|git merge [nome_da_branch] | Combina as alterações da branch especificada na branch em que você está atualmente.|
|git pull origin [nome_da_branch] |Baixa as últimas alterações de um repositório remoto (origin é o nome padrão do remoto) para a sua branch local, e também mescla essas alterações. É um atalho para git fetch e git merge.|
|git push origin [nome_da_branch] | Envia seus commits locais para o repositório remoto (origin). É assim que suas alterações são publicadas no GitHub, por exemplo. |
|git remote -v |Lista os repositórios remotos configurados para o seu projeto.|
|git rm [nome_do_arquivo] | Remove um arquivo do seu diretório de trabalho e do Git.|
|git reset [arquivo] | Remove um arquivo da área de staging (desfaz um git add), mas mantém o arquivo no seu diretório de trabalho. |
|git restore [arquivo] | Descarta as alterações feitas em um arquivo desde o último commit (volta o arquivo ao estado do último commit). |
|git diff | Mostra as diferenças entre o seu diretório de trabalho, a área de staging e o último commit. |## Trabalhar com **branches (ramificações)** é uma das funcionalidades mais poderosas e fundamentais do Git, essencial para o desenvolvimento colaborativo e para manter seu código organizado.

Vamos entender o que são branches e como trabalhar com elas:

-----

### O que são Branches?

Imagine seu projeto Git como uma linha do tempo principal (geralmente chamada de `main` ou `master`). Uma **branch** é como uma "ramificação" dessa linha do tempo. Ela permite que você:

  * **Desenvolva novas funcionalidades** sem afetar o código principal (estável).
  * **Corrija bugs** em um ambiente isolado.
  * **Experimente ideias** sem medo de quebrar o projeto principal.
  * Permita que **várias pessoas trabalhem em diferentes partes** do projeto ao mesmo tempo.

Quando você cria uma branch, é como se estivesse fazendo uma cópia do estado atual do seu projeto. Todas as alterações que você fizer nessa nova branch não afetarão a branch principal até que você decida mesclá-las.

-----

### Fluxo de Trabalho Básico com Branches

Um fluxo de trabalho comum seria:

1.  **Branch Principal (Ex: `main` ou `master`):** Contém a versão estável e funcional do seu projeto.
2.  **Criação de uma Nova Branch:** Para cada nova funcionalidade, correção de bug ou experimento, você cria uma nova branch a partir da principal.
3.  **Desenvolvimento na Nova Branch:** Você trabalha, faz commits e testa suas alterações nessa branch isolada.
4.  **Mesclagem (Merge):** Quando a funcionalidade está pronta e testada, você mescla as alterações da sua branch de volta para a branch principal.
5.  **Exclusão da Branch:** Após a mesclagem, a branch de funcionalidade geralmente é excluída, pois seu propósito foi cumprido.

-----

### Comandos Principais para Trabalhar com Branches

Aqui estão os comandos Git essenciais para gerenciar branches:

1.  **Verificar as Branches Existentes:**

    ```bash
    git branch
    ```

      * Este comando lista todas as branches locais no seu repositório. A branch em que você está atualmente será marcada com um asterisco (`*`).

2.  **Criar uma Nova Branch:**

    ```bash
    git branch [nome_da_nova_branch]
    ```

      * Exemplo: `git branch minha-nova-funcionalidade`
      * Este comando cria a branch, mas **não te move para ela**. Você ainda estará na branch anterior.

3.  **Mudar para uma Branch Existente:**

    ```bash
    git checkout [nome_da_branch]
    # OU (recomendado para versões mais recentes do Git)
    git switch [nome_da_branch]
    ```

      * Exemplo: `git checkout minha-nova-funcionalidade`
      * Exemplo: `git switch minha-nova-funcionalidade`
      * Este comando muda seu diretório de trabalho para o estado da branch especificada.

4.  **Criar e Mudar para uma Nova Branch (Atalho):**

    ```bash
    git checkout -b [nome_da_nova_branch]
    # OU (recomendado para versões mais recentes do Git)
    git switch -c [nome_da_nova_branch]
    ```

      * Exemplo: `git checkout -b minha-nova-funcionalidade`
      * Exemplo: `git switch -c minha-nova-funcionalidade`
      * Este é um comando muito comum, pois ele cria a nova branch e já te move para ela em uma única etapa.

5.  **Mesclar uma Branch em Outra:**

      * Primeiro, **mude para a branch que você quer atualizar** (geralmente a `main` ou `master`).
        ```bash
        git switch main
        ```
      * Em seguida, **mescle a branch de funcionalidade** nela:
        ```bash
        git merge [nome_da_branch_a_mesclar]
        ```
          * Exemplo: `git merge minha-nova-funcionalidade`
          * O Git tentará combinar as alterações automaticamente. Se houver conflitos (partes do código que foram alteradas de forma diferente em ambas as branches), o Git irá notificá-lo, e você precisará resolvê-los manualmente antes de finalizar o merge.

6.  **Excluir uma Branch Local:**

      * **Importante:** Você não pode excluir a branch em que você está atualmente. Mude para outra branch (geralmente `main`) antes de excluir.
      * Para excluir uma branch que já foi mesclada:
        ```bash
        git branch -d [nome_da_branch_a_excluir]
        ```
          * Exemplo: `git branch -d minha-nova-funcionalidade`
      * Para forçar a exclusão de uma branch (mesmo que não tenha sido mesclada, use com cautela, pois pode perder commits):
        ```bash
        git branch -D [nome_da_branch_a_excluir]
        ```

7.  **Enviar uma Branch para o Repositório Remoto (GitHub):**

      * Quando você cria uma branch localmente, ela só existe na sua máquina. Para que ela apareça no GitHub e outros possam vê-la e colaborar, você precisa enviá-la:
        ```bash
        git push -u origin [nome_da_sua_branch]
        ```
          * Exemplo: `git push -u origin minha-nova-funcionalidade`
          * O `-u` (ou `--set-upstream`) é usado na primeira vez para vincular sua branch local à branch remota de mesmo nome. Nas próximas vezes, um simples `git push` já será suficiente.

8.  **Excluir uma Branch no Repositório Remoto (GitHub):**

    ```bash
    git push origin --delete [nome_da_branch_remota]
    ```

      * Exemplo: `git push origin --delete minha-nova-funcionalidade`

-----

### Por que usar Branches?

  * **Isolamento:** Mantenha o código principal limpo e funcional enquanto trabalha em novas funcionalidades.
  * **Colaboração:** Várias pessoas podem trabalhar em paralelo em diferentes branches sem interferir umas nas outras.
  * **Experimentação:** Crie branches para testar ideias radicais ou refatorações sem medo de danificar o projeto principal.
  * **Revisão de Código:** Em plataformas como o GitHub, as branches são a base para **Pull Requests**, onde colegas de equipe podem revisar suas alterações antes que elas sejam mescladas na branch principal.

Dominar o uso de branches é um passo crucial para se tornar proficiente em Git e colaborar efetivamente em projetos de software.

--------
 ## O comando `git fetch` é super importante no fluxo de trabalho Git, especialmente quando você está colaborando em um projeto.

-----

#### `git fetch`: O que faz e por que é importante?

O comando `git fetch` é usado para **baixar as últimas alterações (commits e branches) do repositório remoto para o seu repositório local**, **sem integrá-las** (mesclá-las) ao seu diretório de trabalho atual.

Pense nele como uma "espiada" no que há de novo no repositório remoto sem realmente afetar o que você está trabalhando no momento.

#### Em detalhes:

1.  **Baixa Referências Remotas:** Ele vai até o repositório remoto (ex: GitHub) e busca todas as novas branches e commits que outros colaboradores enviaram desde a última vez que você interagiu com o remoto.
2.  **Atualiza as "Remote-Tracking Branches":** O Git armazena essas informações em branches especiais no seu repositório local, chamadas "remote-tracking branches" (ramos de rastreamento remoto). Por exemplo, se você tem uma branch `main` no remoto chamada `origin`, o `git fetch` irá atualizar a sua branch `origin/main` local.
3.  **Não Altera seu Código Local:** É crucial entender que `git fetch` *não* muda nenhum dos seus arquivos no seu diretório de trabalho ou move sua branch local (por exemplo, sua `main` local). Ele apenas *baixa* as informações.

#### Por que usar `git fetch`?

  * **Verificar Novas Alterações:** É ideal para ver o que os outros estão fazendo no projeto sem precisar integrar essas mudanças imediatamente. Você pode inspecionar os commits recém-chegados antes de decidir mesclá-los.
  * **Preparar para um `pull`:** Muitas vezes, `git fetch` é o primeiro passo para um `git pull`. O `git pull` é, na verdade, um atalho para `git fetch` seguido de `git merge`. Ao usar `git fetch` separadamente, você tem mais controle sobre o processo de mesclagem.
  * **Evitar Conflitos Imediatos:** Se você está no meio de um trabalho importante e não quer que as novas alterações remotas causem conflitos ou bagunças no seu código atual, `git fetch` é a escolha segura. Você pode continuar trabalhando e depois mesclar as alterações remotas quando for conveniente.

#### Sintaxe:

  * **Para buscar de todos os remotos configurados:**
    ```bash
    git fetch
    ```
  * **Para buscar de um remoto específico (ex: `origin`):**
    ```bash
    git fetch origin
    ```
  * **Para buscar de um remoto específico e uma branch específica:**
    ```bash
    git fetch origin [nome_da_branch_remota]
    ```
    *Exemplo:* `git fetch origin develop`

#### Exemplo de uso:

1.  Você está trabalhando na sua branch `minha-funcionalidade`.

    ```bash
    git status
    # On branch minha-funcionalidade
    # Your branch is up to date with 'origin/minha-funcionalidade'.
    # ...
    ```

2.  Enquanto isso, um colega envia novas atualizações para a branch `main` no GitHub.

3.  Você quer ver o que há de novo na `main` remota, mas não quer sair da sua branch ou mesclar as alterações ainda:

    ```bash
    git fetch origin
    ```

    *Saída possível:*

    ```
    From github.com:seu_usuario/seu_repositorio
     * [new branch]      feature-xyz -> origin/feature-xyz
       a1b2c3d..e4f5g6h  main        -> origin/main
    ```

    Isso significa que o Git baixou as informações da `main` remota (atualizando sua `origin/main` local) e talvez até uma nova branch chamada `feature-xyz`.

4.  Agora, você pode comparar sua branch atual com a `origin/main` para ver as diferenças:

    ```bash
    git diff minha-funcionalidade origin/main
    ```

5.  Quando você estiver pronto para incorporar as mudanças da `main` no seu trabalho, você pode fazer:

    ```bash
    git checkout main       # Mude para a branch main
    git pull origin main    # Baixe e mescle as alterações da main remota
    # OU
    # git merge origin/main # Se você já fez um git fetch anteriormente
    ```

Em resumo, `git fetch` é a sua ferramenta para manter seu repositório local "ciente" das novidades do remoto, mas sem o compromisso imediato de integrá-las ao seu código de trabalho. É uma boa prática usar `git fetch` antes de iniciar um novo trabalho ou antes de fazer um `git pull` em uma branch importante.