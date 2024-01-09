# Github flow

<img width="649" alt="image" src="https://github.com/lsmatias/githubflow/assets/28391885/852e749d-ad00-47ec-aa6d-eaafb43d7c12">


--------------------------------------------------------------------------------------
GitHub Flow é um modelo de fluxo de trabalho leve, simplificado e centrado em integração contínua. Suas principais características incluem:

:bookmark: Branches Principais Simples

:label: Feature Branches

:outbox_tray: Pull Requests (Solicitações de Mesclagem)

:rocket: Deploy Contínuo

--------------------------------------------------------------------------------------

## :bookmark: Branches Principais Simples

Normalmente, há apenas dois branches principais: main ou master e branches de feature.
        
        (main)
          |
          ↓
    o --- o --- o --- o    (main)
                 \
                  \        (feature1) 
                   o --- o --- o    (featurenova-funcionalidade)

Neste diagrama:

* (main) é o branch principal, representando o estado atual e estável do projeto.

* (feature1) é um branch de feature, onde você está trabalhando em uma nova funcionalidade ou alteração.

## :label: Feature Branches

Agora, você deseja adicionar uma nova funcionalidade ao projeto. Então, agora nossa **Feature1** vai ser chamar **feature/nova-funcionalidade** e vamos criar  a partir do branch principal main:

    (main)
      |
      ↓
      o ----   Feature/featurenova-funcionalidade
             \
              \        
               o --- Commits: Implementação da nova funcionalidade
               
Durante o desenvolvimento, você pode realizar quantos commits forem necessários para completar a funcionalidade, mantendo todas essas alterações isoladas na sua feature branch.

## :outbox_tray: Pull Requests (Solicitações de Mesclagem): 
As alterações feitas em feature branches são mescladas de volta ao branch principal por meio de pull requests. Antes da mesclagem, é comum revisar o código e realizar testes.

Suponhamos que você tenha um main estável e tenha trabalhado em uma nova funcionalidade no branch feature/branch1. Após concluir suas alterações e antes de mesclar as mudanças no main, você abre um Pull Request (PR) no GitHub.
                                       
                                        (Pull Request)
                                              |
                                              v
              o --- o --- o --- o    (main)
                   \
                    \
                     o --- o --- o    (feature/featurenova-funcionalidade)
Nesse ponto, o Pull Request permite que outros membros da equipe revisem o código, façam comentários, sugiram alterações ou realizem testes adicionais no código das alterações feitas no feature/branch1.

Após revisões, testes e aprovações, você está pronto para mesclar as alterações de feature/branch1 de volta ao main.
                                        
                                        (Pull Request)       
                                              |
                                              v
              o --- o --- o --- o --- o --- o    (main)
                   \                       /
                    \                     /
                     o --- o --- o --- o    (feature/featurenova-funcionalidade)

Finalmente, uma vez que o Pull Request foi revisado e aprovado, as alterações são mescladas no main. O main agora contém as novas funcionalidades implementadas no branch feature/branch1.

                                         (Pull Request aprovado)
                                              |
                                              v
              o --- o --- o --- o --- o --- o    (main)
                   \                       /
                    \                     /
                     o --- o --- o --- o    (feature/featurenova-funcionalidade)
## :rocket: Deploy Contínuo
Após o merge do Pull Request, algumas equipes configuram seus processos de CI/CD (Integração Contínua/Implantação Contínua) para serem acionados automaticamente. Isso significa que, com a conclusão bem-sucedida do merge, o pipeline de CI/CD é disparado para implantar o código atualizado no ambiente de produção.

                                        (Pipeline de CI/CD acionado)
                                              |
                                              v
              o --- o --- o --- o --- o --- o    (main) --> (Deployed to Production)
                   \                       /
                    \                     /
                     o --- o --- o --- o    (feature/featurenova-funcionalidade)


A partir desse ponto, o código que foi mesclado no main é automaticamente implantado no ambiente de produção. Esse processo de implantação pode variar de acordo com as práticas e ferramentas específicas que uma equipe utiliza para fazer a implantação. Esse processo de Pull Request no GitHub Flow é fundamental para garantir a qualidade do código, colaboração entre membros da equipe e a integridade do branch principal antes de incorporar novas alterações.

# Resumo do Fluxo completo

:white_check_mark: Branch main: É o branch principal do repositório, representando a versão estável do código em produção.

:white_check_mark: Feature Branches: Desenvolvimento de novas funcionalidades acontece em branches separadas (feature branches) originadas a partir do main. Cada funcionalidade ou tarefa é trabalhada em seu próprio branch.

:white_check_mark: Pull Requests (PRs): Quando a funcionalidade está pronta para ser integrada ao main, é criado um Pull Request para revisão do código. Isso permite revisão, discussão e testes antes da mesclagem.

:white_check_mark: Merge no main: Após a revisão e aprovação, a funcionalidade é mesclada de volta ao main, ativando um processo de implantação contínua.

É importante ressaltar que a implantação automática após o merge nem sempre é uma prática adotada por todas as equipes. Algumas podem optar por um acionamento manual ou algum tipo de etapa de aprovação adicional antes de realizar o deploy para produção. O GitHub Flow é flexível e pode ser adaptado de acordo com as necessidades e políticas específicas de cada equipe ou projeto.
