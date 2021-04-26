# Conventional Commits
## Saiba mais
- [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/)
- [Angular Conventional](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines)
- [Semantic Versioning](https://semver.org/lang/pt-BR/)
- [Commitizen Command Line](https://github.com/commitizen/cz-cli)
- [Commitizen friendly](http://commitizen.github.io/cz-cli/)

## O que é?
- É uma especificação simples de mensagens que seguem um conjunto de regras para estruturar as mensagens de commit.

## Quais os benefícios?
- Automatiza a criação de CHANGELOGs.
- Melhora o entendimento sobre a concentração de atividades do projeto.
- Ajuda na entrada de novas pessoas no projeto através da padronização das mensagens.

## Como utilizar?
### A mensagem de ser estruturada da seguinte forma:

```
<tipo>(<escopo> opcional): <descrição>
<LINHA EM BRANCO>
<body opcional>
<LINHA EM BRANCO>
<rodapé opcional>
```

### Regras básicas
1. Tipo é obrigatório.
2. Escopo é opcional, deve ser um substantivo e estar entre parenteses
3. Se houver mais de um escopo os mesmos devem ser separados por "\\", "/" ou ",".
4. Após o tipo e escopo devemos colocar o dois-pontos e um espaço.
5. A descrição sempre inicia com letra minúscula e deve ser curta (até 80 caracteres)
6. Um corpo mais longo pode ser fornecido e deve começar depois de uma linha em branco.
7. Um rodapé com uma ou mais linhas pode ser fornecido e deve começar depois de uma linha em branco.
8. Quebras de compatibilidades devem ser informadas no corpo após o texto BREAKING CHANGE: <descrição>.
9. O caractere ! pode ser usado para chamar atenção de quebra de compatibilidade. Ele deve ser adicionado antes do dois-pontos da primeira linha do commit.

### Os tipos
> O **tipo** é responsável por nos dizer qual o tipo de alteração ou iteração está sendo feita, das regras da convenção, temos os seguintes tipos:

- **test:** indica qualquer tipo de criação ou alteração de códigos de teste.<br>
_Exemplo: Criação de testes unitários._
- **feat:** indica o desenvolvimento de uma nova feature ao projeto.<br>
_Exemplo: Acréscimo de um serviço, funcionalidade, endpoint, etc._
- **refactor:** usado quando houver uma refatoração de código que não tenha qualquer tipo de impacto na lógica/regras de negócio do sistema.<br>
_Exemplo: Mudanças de código após um code review_
- **style:** empregado quando há mudanças de formatação e estilo do código que não alteram o sistema de nenhuma forma.<br>
_Exemplo: Mudar o style-guide, mudar de convenção lint, arrumar indentações, remover espaços em brancos, remover comentários, etc._
- **fix:** utilizado quando há correção de erros que estão gerando bugs no sistema.<br>
_Exemplo: Aplicar tratativa para uma função que não está tendo o comportamento esperado e retornando erro._
- **chore:** indica mudanças no projeto que não afetem o sistema ou arquivos de testes. São mudanças de desenvolvimento.<br>
_Exemplo: Mudar regras do eslint, adicionar prettier, adicionar mais extensões de arquivos ao .gitignore_
- **docs:** usado quando há mudanças na documentação do projeto.<br>
_Exemplo: adicionar informações na documentação da API, mudar o README, etc._
- **build:** utilizada para indicar mudanças que afetam o processo de build do projeto ou dependências externas.<br>
_Exemplo: Gulp, adicionar/remover dependências do npm, etc._
- **perf:** indica uma alteração que melhorou a performance do sistema.<br>
_Exemplo: alterar ForEach por while, melhorar a query ao banco, etc._
- **ci:** utilizada para mudanças nos arquivos de configuração de CI.<br>
_Exemplo: Circle, Travis, BrowserStack, etc._
- **env:** basicamente utilizado na descrição de modificações ou adições em arquivos de configuração em processos e métodos de integração contínua (CI).
_Exempo: Alteração em parâmetros em arquivos de configuração de containers._
- **revert:** indica a reverão de um commit anterior.<br>

### Exemplos de mensagens de commit

- Mensagem de commit com descrição e modificação que quebra a compatibilidade no rodapé
```
feat: permitir que o objeto de configuração fornecido estenda outras configurações

BREAKING CHANGE: a chave `extends`, no arquivo de configuração, agora é utilizada para estender outro arquivo de configuração
```

- Mensagem de commit com ! para chamar a atenção para quebra a compatibilidade
```
refactor!: remove suporte para Node 6
```

- Mensagem de commit com ! e roadapé BREAKING CHANGE
```
refactor!: remove suporte para Node 6

BREAKING CHANGE: refatorar para usar recursos do JavaScript não disponíveis no Node 6.
```

- Mensagem de commit sem corpo
```
docs: ortografia correta de CHANGELOG
```

- Mensagem de commit com escopo
```
feat(lang): adiciona tradução para português brasileiro
```

- Mensagem de commit com vários escopos
```
feat(lang/resource): adiciona tradução para português brasileiro no arquivo de resource pt-br
```

- Mensagem de commit de uma correção utilizando número de ticket (opcional)
```
fix: corrige pequenos erros de digitação no código

veja o ticket para detalhes sobre os erros de digitação corrigidos

Revisado por: Daniel Nass
Refs #133
```

## Commitizen
> É um pacote que facilita a criação de mensagens de commit seguindo a especificação **Conventional Commits**.

### Requisitos
#### No Ubuntu
```sh
sudo apt update -y
sudo apt install git -y
sudo apt install npm -y
sudo apt install nodejs -y
```
#### No Windows
- https://nodejs.org/en/download/

### Instalação
```sh
sudo npm install -g commitizen
sudo npm install -g cz-conventional-changelog
```

### Configurando o repositório
```sh
git init # crie ou clone um novo repositorio
echo '{ "path": "cz-conventional-changelog" }' > .czrc # criar arquivo na raiz do projeto
mkdir sample-app
cd sample-app
```

### Exemplo: Primeiro commit
```sh
echo teste >> arquivo_1.txt
git add .
git cz
```
