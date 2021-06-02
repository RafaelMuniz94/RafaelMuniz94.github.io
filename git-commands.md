O Git é uma ferramenta de versionamento de código, sendo a mais utilizada atualmente.

Foi criada para armazenar o Kernel do linux com a finalidade de gerenciar de maneira eficiente o código dos diversos desenvolvedores.

___
# Conceitos

## Versionamento de Código

O versionamento de código é uma prática que já ocorria antes do git, foi criada devido a necessidade de dividir o trabalho para equipes e facilitar e organizar a forma que o fonte era armazenado.

Com a prática do versionamento podemos retornar para momentos anteriores de código ou podemos realizar testes sem que o código pare de funcionar, pois caso isso ocorra basta jogar fora as mudanças realizadas.

## Checksum

Soma de verificações, esse é o conceito que está no nível mais baixo do git e que garante sua eficiencia e segurança, graças a esse conceito é impossivel que qualquer assunto no repositório seja alterado sem que o git saiba.

O Checksum também verifica os arquivos durante a transmissão do mesmo, evitando que qualquer arquivo corrompido seja recebido.

O mecanismo utiliza um hash SHA-1 de 40 caracteres hexadecimais.

Os arquivos salvos pelo git são referenciados através dessa hash e não de seus nomes.

## Commit
Um commit é a consolidação das alterações que aquele repositório teve, podendo ser apenas um ou mais arquivos. 

É importante entender que o git é um sistema de versionamento de arquivos, sendo assim uma pasta não é versionada caso a mesma esteja vazia. 
> Dica: Não existe um momento certo para realizar um commit, o mesmo deve ser feito apenas quando o código estiver pronto para build e funcional, evitar commits muito grande também é uma boa prática.

## Servidor Remoto (Remote)

Um servidor remoto não encontra-se na máquina do desenvolvedor, geralmente está em um servidor onde diversos contribuintes podem acessar e realizar o versionamento de suas alterações.

Um servidor remoto pode ser próprio de uma empresa, onde apenas funcionários e usuários com acesso à aquele domínio irão conseguir acessar ou podem ser públicos como [GitHub](https://github.com/), onde desenvolvedores do mundo todo podem criar e contribuir para projetos privados ou públicos. 

Cada repositório git pode estar associado a nenhum ou N repositórios remoto, sendo assim pode haver cenários onde o código deve ser baixado por um servidor e enviado para outro.
___
# Comandos básicos

> Observação: para comandos que travem o terminal, utilizar a tecla q para sair e setas para navegar.
## `git init`
-   Inicia o repositorio git e começa seu versionamento
    -   `git init` -- bare
        -   Indica que o repositório não irá conter uma cópia de cada arquivo modificado, armazenando apenas os hashs das mudanças.
        > Indicado para servidores remoto, sendo estes puros onde os arquivos não serão alterados
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

## `git remote`
  -  Quando o repositório local conhecer algum endereço remoto, este comando irá mostrar todos os remotos pelo nome.
     -  ### `git remote add` [nome_server_remoto] [endereço_remoto]
        -  Adiciona um remoto ao repositório local, esse remoto pode ser algum outro repositório, pasta na rede, servidor.
        > Sempre que um repositório for clonado, o local irá conter o histórico e os remotos do repositório de origem.
---
# Arquivos

Existem alguns arquivos que podem ser associados ao git, sendo esses tanto de configuração ou utilitários.

## .gitignore
Esse arquivo deve conter tudo aquilo que o git não deverá versionar, dessa forma impedimos que o git acabe subindo informações desnevessárias para os demais usuários.

Cada linha deve representar um diretório, extensão ou até mesmo um arquivo específico.

Deve estar na raiz de um repositório versionado, o ideal é que seja criado durante o primeiro commit do projeto.

> Dica: Cada linguagem/framework possui arquivos específicos e que podem ser ignorados por padrão, podemos também incluir aqui arquivos de configuração.
>> É recomendado que esse arquivo já esteja presente durante os commits iniciais, para evitar que por engano informações sensíveis ou irrelevantes ao projeto sejam versionadas.

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