O Git é uma ferramenta de versionamento de código, sendo a mais utilizada atualmente.

Foi criada para armazenar o Kernel do linux com a finalidade de gerenciar de maneira eficiente o código dos diversos desenvolvedores.

___
# Conceitos

## Commit
Um commit é a consolidação das alterações que aquele repositório teve, podendo ser apenas um ou mais arquivos. 

É importante entender que o git é um sistema de versionamento de arquivos, sendo assim uma pasta não é versionada caso a mesma esteja vazia. 
>Dica: Não existe um momento certo para realizar um commit, o mesmo deve ser feito apenas quando o código estiver pronto para build e funcional, evitar commits muito grande também é uma boa prática.
___
# Comandos básicos

> Observação: para comandos que travem o terminal, utilizar a tecla q para sair e setas para navegar.
## `git init`
-   Inicia o repositorio git e começa seu versionamento
## `git add` [arquivo/pasta]
-   Adiciona arquivo ao versionamento do git
-   Inicia o track sobre o arquivo caso o mesmo seja novo, antes disso o mesmo **não** está no controle de versão.
> Dica: Apenas arquivos salvos irão ser adicionados, assim como pastas que possuem arquivo (caso a pasta deva estar em branco vide o arquivo `.gitkeep`)

## `git status`
- Mostra as diferenças entre o ultimo commit e o atual, informando se arquivos foram alterados, incluídos ou removidos.
  > Dica: rodar esse comando antes de executar o commit para verificar se todas as mudanças foram versionadas, caso alguma não esteja utilizar o comando `git add`
## `git commit -m` ["mensagem"]
-   Cria um commit com a mensagem passada
-   Salva as alterações na branch local
## `git log` 
-   Mostra o historico de commits
    -   ### `git log` --oneline
        -   mostra o log de commits em apenas uma linha
    - ### `git log` -p
      - mostra a log com mais informações, incluindo oque foi modificado
    - ### `git log` --pretty=[log_format]
      - mostra a log da maneira configurada definida pelo formato escolhido
    - ### `git log` --help
      - mostra recursos de log
## `git config` [escopo] [configuração]
-   Modifica uma configuração em um determinado escopo
    - ### --local [configuração]
      -   Troca a config passada localmente (apenas para aquele projeto)

---
# Arquivos

## .gitignore
Esse arquivo deve conter tudo aquilo que o git não deverá versionar, dessa forma impedimos que o git acabe subindo informações desnevessárias para os demais usuários.

Cada linha deve representar um diretório, extensão ou até mesmo um arquivo específico.

Deve estar na raiz de um repositório versionado, o ideal é que seja criado durante o primeiro commit do projeto.

>Dica: Cada linguagem/framework possui arquivos específicos e que podem ser ignorados por padrão, podemos também incluir aqui arquivos de configuração.

## .gitkeep
Esse é um arquivo para versionar pastas que não possuem fonte ou asset, sendo assim, ao criar esse arquivo a pasta será versionada.

Não é necessário inserir nenhum conteúdo no arquivo para que ele esteja funcional.
___
### Documentação oficial
- [SCM](https://git-scm.com/)
- [Download e Instalação](https://git-scm.com/downloads)
- [Manual de Referência](https://git-scm.com/docs)
- [Livro Pro Git](https://git-scm.com/book/en/v2)
- [Livro Pro Git (Português)](https://git-scm.com/book/pt-br/v2)
---
#### Cheatsheet
1. [log](https://devhints.io/git-log)
2. [log format](https://devhints.io/git-log-format)
3. [extras](https://devhints.io/git-extras)
4. [tricks](https://devhints.io/git-tricks)