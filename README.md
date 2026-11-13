# Margem — espaço de escrita

<p align="center">
  <strong>Um lugar calmo para as palavras.</strong><br>
  Seus textos ficam com você.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-em%20evolu%C3%A7%C3%A3o-58765e" alt="Status: em evolução">
  <img src="https://img.shields.io/badge/HTML5-CSS3%20%7C%20JavaScript-6b8b70" alt="HTML, CSS e JavaScript">
  <img src="https://img.shields.io/badge/PWA-Manifest%20%2B%20Service%20Worker-465b4b" alt="Recursos PWA">
</p>

---

## Sobre o projeto

**Margem** é um espaço digital de escrita individual. A proposta é oferecer uma interface tranquila para criar, organizar e continuar textos sem depender de uma conta ou de um serviço na nuvem.

Os documentos são salvos no armazenamento local do navegador. O projeto também possui um manifesto de aplicação web e um Service Worker que armazena em cache a estrutura do site e recursos da mesma origem, permitindo reabrir a aplicação quando a conexão estiver indisponível, depois do primeiro acesso com carregamento em rede.

## Funcionalidades implementadas

- **Criar documentos:** iniciar uma página em branco, um diário com a data atual ou uma nota rápida para registrar uma ideia.
- **Editor de texto:** escrever diretamente na página e aplicar negrito, itálico, sublinhado, parágrafos, título e listas ordenadas ou não ordenadas.
- **Salvamento automático local:** as alterações são persistidas no navegador após uma breve pausa na digitação.
- **Contagem de palavras:** acompanhar a quantidade de palavras do documento aberto.
- **Biblioteca:** visualizar todos os textos, acessar os documentos recentes (atualizados nos últimos sete dias) e consultar os favoritos.
- **Navegação responsiva:** acesso aos filtros principais também em telas menores.
- **Favoritos:** marcar e desmarcar documentos.
- **Exclusão de documentos:** remover um texto com confirmação antes da ação.
- **Exportação individual:** baixar um documento como arquivo TXT.
- **Backup da biblioteca:** exportar todos os documentos em um arquivo JSON.
- **Uso offline:** o Service Worker armazena a estrutura principal e recursos GET da mesma origem em cache.

## Armazenamento e privacidade

O Margem não utiliza backend, banco de dados remoto ou sincronização entre dispositivos nesta versão.

Os documentos ficam no **localStorage** do navegador, associados à chave **margem-documents-v1**. Por isso:

- os textos permanecem no navegador e dispositivo em que foram criados;
- limpar os dados do site ou o armazenamento do navegador pode apagar os documentos;
- abrir o Margem em outro dispositivo ou navegador não transfere automaticamente os textos;
- recomenda-se utilizar a opção de backup JSON ou exportar documentos importantes em TXT.

O indicador de conexão informa o estado online/offline; ele não representa sincronização com um servidor.

## Tecnologias e recursos

| Tecnologia / recurso | Utilização |
|---|---|
| HTML5 | Estrutura da aplicação e áreas de navegação |
| CSS3 | Layout, componentes, editor e adaptação para telas menores |
| JavaScript | Criação de documentos, edição, filtros, favoritos, contagem e exportação |
| localStorage | Persistência local dos documentos |
| Web App Manifest | Metadados e comportamento de abertura da aplicação |
| Service Worker | Cache da estrutura e de requisições GET da mesma origem |
| Google Fonts | Tipografia DM Sans, DM Serif Display e Source Serif 4 |

A aplicação não utiliza framework ou processo de build nesta versão. O manifesto ainda não declara ícones próprios; a experiência de instalação pode variar conforme o navegador.

## Estrutura do repositório

~~~text
Margem/
├── index.html       # Interface, estilos e lógica principal da aplicação
├── manifest.json    # Metadados da aplicação web
├── sw.js            # Cache e suporte de carregamento offline
├── LICENSE          # Licença do projeto
└── README.md        # Documentação
~~~

## Como executar localmente

O Margem é uma aplicação estática. Não é necessário instalar pacotes com npm.

### 1. Clonar o repositório

~~~bash
git clone https://github.com/Amanda-AAndrade/Margem.git
~~~

### 2. Acessar a pasta

~~~bash
cd Margem
~~~

### 3. Iniciar um servidor local

**Windows (Python 3):**

~~~powershell
py -m http.server 5500
~~~

**Linux ou macOS (Python 3):**

~~~bash
python3 -m http.server 5500
~~~

### 4. Abrir no navegador

Acesse:

~~~text
http://localhost:5500
~~~

Também é possível abrir a pasta no Visual Studio Code e utilizar a extensão Live Server. O Service Worker requer um contexto seguro: HTTPS em publicação ou localhost durante o desenvolvimento.

## Comandos úteis

Verificar o estado do repositório:

~~~bash
git status
~~~

Atualizar a cópia local:

~~~bash
git pull origin main
~~~

Registrar e enviar alterações:

~~~bash
git add .
git commit -m "docs: atualiza documentação do Margem"
git push origin main
~~~

Não é necessário executar npm install para utilizar a versão atual.

## Publicação

O projeto pode ser acessado pelo GitHub Pages:

**[Abrir Margem](https://amanda-aandrade.github.io/Margem/)**

Para publicar pelo GitHub Pages, configure o repositório em **Settings → Pages**, selecione a branch main e a pasta raiz (/ root).

## Próximas evoluções possíveis

- [ ] Adicionar ícones próprios ao Web App Manifest.
- [ ] Melhorar o fluxo de instalação e a apresentação do estado offline.
- [ ] Criar opções de importação e restauração do backup JSON.
- [ ] Permitir exportação em formatos adicionais.
- [ ] Avaliar recursos de acessibilidade e experiência do editor.
- [ ] Considerar sincronização entre dispositivos apenas se houver uma futura camada de backend.

## Desenvolvimento

Projeto desenvolvido por **Amanda Andrade** como aplicação web de escrita, com foco em armazenamento local, experiência simples e recursos progressivos da plataforma web.

---

<p align="center"><strong>Margem — seus textos, no seu ritmo.</strong></p>
