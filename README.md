
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
|git diff | Mostra as diferenças entre o seu diretório de trabalho, a área de staging e o último commit. |