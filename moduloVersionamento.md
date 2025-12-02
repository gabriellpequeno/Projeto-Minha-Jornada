
# Uma Jornada de Aprendizado

[Modulo Introcução a Redes](./moduloRedes.md)

  
  

## Parte 1 | O que é Controle de Versão?

  

### Sistema de Controle de Versão

Um Sistema de Controle de Versão (VCS) é uma ferramenta que rastreia e gerencia as mudanças em arquivos ao longo do tempo. Ele permite que os usuários voltem a versões anteriores de um projeto, comparem alterações e trabalhem em paralelo sem sobrescrever o trabalho uns dos outros.

  

Esses sistemas são usados para manter o histórico de um projeto organizado, funcionando como uma "máquina do tempo" que permite recuperar estados anteriores do código ou de qualquer outro tipo de arquivo.

  

### O que é o Git?

O **Git é um Sistema de Controle de Versão Distribuído** projetado para lidar com projetos de todos os tamanhos com velocidade e eficiência.

  

Ele mantém um histórico completo e detalhado de todas as mudanças feitas nos arquivos, permitindo não apenas **reverter para versões antigas, mas também entender exatamente o que mudou entre elas**

  

#### Conceitos Fundamentais

-  **Repositório**

Uma pasta que contém todo o projeto e o histórico de suas revisões.

Pode ser local (na máquina do usuário) ou remoto (hospedado na internet).

  

-  **Commit**

Um "ponto de checagem" seguro ou um instantâneo do estado do projeto em um determinado momento.

Cada commit armazena as alterações feitas e é identificado por um hash único.

  

-  **HEAD**

Um ponteiro que indica qual branch está selecionada no momento.

Ele aponta para o último commit da branch ativa, determinando onde o próximo commit será adicionado.

  

## Parte 2 | Fluxo de Trabalho Básico com Git

  

O fluxo de trabalho básico do Git envolve três áreas principais:

  

1.  **Working Tree (Árvore de Trabalho):**

O diretório onde os arquivos são modificados.

  

2.  **Index (Staging Area):**

Uma área intermediária onde as mudanças são preparadas para serem incluídas no próximo commit.

3.  **Repositório Local:**

Onde o histórico de commits é armazenado.

  
  

#### Comandos Essenciais

  
  

| Comando | Função |
|--|--|
| `git init` | Inicializa um novo repositório Git em uma pasta local. |
| `git status` | Mostra o estado dos arquivos na Working Tree e no Index. |
| `git add <nomeDoArquivo>` | Adiciona as mudanças de um arquivo da Working Tree para o Index (Staging Area). |
| `git commit -m <mensagem>` | Cria um novo commit com as mudanças que estão no Index. |
| `git log` | Exibe o histórico de commits da branch atual. |

  
  
  
  

## Parte 3 | Gerenciamento de Branches e Mesclagem (Merge)

  

### O Conceito de Branch

Uma **Branch (ramificação)** é um marcador que aponta para um commit.

  

Ela permite que o desenvolvimento de novas funcionalidades ou correções seja feito de forma isolada do código principal.

  

-  **Branch main:**

Por convenção, é considerada a versão de produção, estável e pronta para ser distribuída.

  

-  **Outras Branches:**

Usadas para commits de "rascunho" ou desenvolvimento, que ainda não estão finalizados ou testados.

  

#### Comandos Essenciais

| Comando | Função |
|--|--|
| `git branch <nomeBranch>` | Cria uma nova branch para o repositório. |
| `git checkout <branch>` | Move o ponteiro HEAD para a branch especificada. |
| `git checkout -b <nomeBranch>` | Cria uma nova branch e transfere o HEAD para ela. |
| `git switch -c <nomeBranch>` | Cria uma nova branch e transfere o HEAD para ela *(versão mais moderna)*. |

  

### Mesclagem (Merge)

A mesclagem é o processo de integrar as mudanças de uma branch em outra.

  

| Tipo de Merge | Descrição |

|--|--|

| **Fast-Forward** | Ocorre quando a branch de destino não teve novos commits desde que a branch de origem foi criada. O Git simplesmente move o ponteiro da branch de destino para o commit mais recente da branch de origem. |

| **Three-Way** | Ocorre quando ambas as branches tiveram commits independentes desde o ponto de ramificação. O Git cria um novo commit (merge commit) que combina as alterações de ambas as branches. |

  
  

#### Conflitos de Merge

  

Um **conflito de merge** acontece quando o Git não consegue combinar automaticamente as alterações de duas branches porque ***as mesmas linhas de código foram modificadas de maneiras diferentes.***

  

Nesses casos, o usuário deve **intervir manualmente** para resolver o conflito, editando o arquivo para escolher qual versão manter.

  
  

## Parte 4 | Repositórios Remotos e Colaboração

  

Um **Repositório Remoto** é uma versão do projeto hospedada na internet, servindo a dois propósitos principais:

  

1.  **Backup:**

Garante que o histórico de commits e branches/tags esteja seguro, mesmo que a pasta local seja perdida.

  

2.  **Colaboração:**

Permite que múltiplos desenvolvedores trabalhem no mesmo projeto, sincronizando suas alterações através do repositório central.

  

#### Serviços de Hospedagem

Existem vários serviços que hospedam repositórios Git, sendo os mais populares: **GitHub, GitLab e Bitbucket**.

  

Esses serviços não são o Git em si, mas plataformas que se integram ao Git para facilitar a colaboração, revisão de código e integração contínua.

  

#### Serviços de Hospedagem

A comunicação com o repositório remoto é feita através de comandos especializados:

  

| Comando | Função |
|--|--|
| `git remote add <apelido> <url>` | Adiciona um link para o repositório remoto ao projeto local (o apelido padrão é origin). |
| `git clone <url>` | Cria uma cópia local completa de um repositório remoto existente. |
| `git fetch` | Baixa as modificações do repositório remoto, mas não as integra ao código loca. |
| `git push` | Envia os commits do repositório local para o repositório remoto. |
| `git pull` | É uma combinação de git fetch e git merge, baixando e integrando as modificações do remoto ao repositório loca. |

  ## Parte 5 | Fluxo de Colaboração Avançado (Pull Request)

O **Pull Request (PR)** é um mecanismo central em plataformas como o GitHub para gerenciar a integração de código, promovendo **Comunicação, Organização e Automação** no fluxo de trabalho.

#### O que é um Pull Request?

Um PR é uma solicitação formal para mesclar as alterações de uma branch (tópico) em outra (base), geralmente a main. Ele notifica os colaboradores sobre as mudanças feitas e permite que o código seja revisado antes de ser integrado.

#### Benefícios do Pull Request
| Benefício | Descrição |
|--|--|
| Comunicação | Permite que colaboradores discutam e revisem as alterações diretamente na plataforma, sem a necessidade de ferramentas externas. |
| Organização | Possibilita restringir o merge, exigindo aprovações ou testes automatizados antes da integração do código. |
| Automação | Integração com ferramentas de CI/CD (Continuous Integration/Continuous Delivery), como o GitHub Actions, para executar testes automatizados. |

#### Revisão (Review) de Código

A revisão de código é uma etapa crucial do PR, onde colaboradores analisam as alterações propostas.

 - **Status de Revisão:**
 Uma revisão pode ter três status
		 - **Comentário:**
		 Envia feedback geral sem aprovar ou solicitar alterações.
		- **Aprovação:**
		Aprova a mesclagem das alterações.
		- **Solicitação de Alterações:**
		Envia comentários que precisam ser resolvidos antes do merge.
 - **Solicitação de Revisão:**
 Colaboradores podem solicitar a revisão de indivíduos ou equipes específicas, garantindo que o código seja analisado por especialistas na área.

#### Comparação de Branches (Diff)
A ferramenta de comparação (Diff) mostra exatamente o que foi alterado entre a branch de tópico e a branch base.
| Tipo de Comparação | Descrição |
|--|--|
|Dois Pontos `git diff A..B` | Mostra a diferença entre o estado mais recente da branch base (A) e a versão mais recente da branch de tópico (B). |
| Três Pontos `git diff A...B` | Mostra a diferença entre o commit comum mais recente (base de mesclagem) e a versão mais recente da branch de tópico. É o padrão em PRs, pois foca no que a PR realmente introduz. |

#### Resolução de Conflitos em PRs
Conflitos em PRs ocorrem quando o mesmo arquivo foi alterado de forma diferente nas branches. Embora a plataforma possa indicar o conflito, a resolução deve ser feita manualmente pelo desenvolvedor, geralmente seguindo os passos:

 1. Mudar para a branch de tópico `git checkout <branch-topico>`.

2. Mesclar a branch base na branch de tópico `git merge <branch-base>`.

3. Resolver os conflitos manualmente nos arquivos.

4. Fazer um novo commit e enviar as alterações resolvidas `git push`.

#### Autenticação Remota (SSH)
Para enviar um repositório local a um serviço como o GitHub, é comum usar um par de chaves SSH (pública e privada) para autenticação, em vez de nome de usuário e senha. A chave pública é registrada no serviço, e a chave privada permanece no computador do usuário, garantindo uma comunicação segura e autenticada.