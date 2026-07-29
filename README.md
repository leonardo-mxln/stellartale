# 🌌 STELLARTALE // Archive System

> **StellarTale** é uma enciclopédia/wiki interativa de ficção científica (Sci-Fi) com interface temática de terminal retro/CRT (Cathode Ray Tube). O projeto funciona como uma **Single Page Application (SPA)** leve, sem dependência de frameworks pesados, renderizando conteúdos dinamicamente a partir de arquivos planos.

🌐 **Acesse o projeto online:** https://leonardo-mxln.github.io/stellartale

---

## 🛠️ Arquitetura do Projeto

O sistema foi desenvolvido utilizando apenas **HTML5, CSS3 puro e JavaScript Vanilla**, priorizando alta performance, fácil manutenção e portabilidade no GitHub Pages.

Estrutura de diretórios:
- `index.html`: Core/Engine do terminal (Interface fixa)
- `README.md`: Documentação do projeto
- `wiki/`: Banco de dados de verbetes
  - `menu.json`: Mapeamento e índice do menu lateral
  - `inicio.txt`: Conteúdo da página inicial
  - `imagens/`: Repositório de mídias do universo
  - `[categoria]/`: Subpastas de verbetes (ex: faccoes/, planetas/)

---

## 🚀 Como Funciona o Sistema

### 1. O Motor Central (index.html)
O `index.html` atua como a carcaça e o motor do sistema. Ele nunca precisa ser alterado para adicionar novos conteúdos. Ele é responsável por:
- Renderizar a estética de terminal retro CRT (efeitos de Scanline, Glow e fontes monospaçadas).
- Gerenciar temas e estilos visuais via variáveis CSS.
- Processar a navegação dinâmica através da função `loadContent(id)`.

### 2. Navegação e Sumário (wiki/menu.json)
O menu lateral é gerado dinamicamente através do arquivo `menu.json`. Cada item do menu define um `id`, um `title` (título visível) e o `file` (caminho para o arquivo `.txt` correspondente).

### 3. Os Verbetes (.txt com marcação HTML)
Todos os arquivos de texto dentro da pasta `wiki/` são fragmentos contendo marcação HTML e variáveis de estilo do terminal. Quando o usuário clica em uma opção do menu ou aciona um link interno, o JavaScript busca o arquivo `.txt` via `fetch()` e injeta o conteúdo diretamente na tela do terminal.

---

## 🎨 Variáveis de Estilo e Padrão Visual

Para manter a identidade visual do terminal em todos os verbetes, utilize as variáveis CSS nativas do sistema nos seus arquivos `.txt`:

- `var(--main-color)` — Cor principal do terminal (textos de destaque, bordas, títulos).
- `var(--accent-color)` — Cor de sotaque (subtítulos, avisos, dados secundários).
- `var(--dim-color)` — Cor escura/suave (divisores, fundos de caixas).
- `var(--bg-color)` — Cor de fundo principal.

---

## 📝 Como Adicionar ou Editar Conteúdos

### Para criar um novo verbete:
1. **Crie o arquivo `.txt`:** Escreva o conteúdo dentro de `wiki/` ou uma subpasta (ex: `wiki/planetas/marte.txt`).
2. **Adicione as imagens:** Salve as mídias em `wiki/imagens/` e referencie-as no `.txt` utilizando o caminho `./wiki/imagens/nome-da-imagem.png`.
3. **Atualize o Menu:** Insira a nova entrada no arquivo `wiki/menu.json`.

### Para editar uma página existente:
1. Localize o arquivo `.txt` correspondente dentro da pasta `wiki/`.
2. Realize as edições no arquivo e faça o *commit*. O site atualizará o conteúdo automaticamente sem necessidade de mexer na estrutura do código.

---

## 💻 Desenvolvimento Local

Como o projeto utiliza a API `fetch()` para carregar os arquivos `.txt` e `.json`, é necessário rodá-lo através de um servidor local para evitar bloqueios de CORS do navegador.

1. Clone o repositório:
   `git clone https://github.com/leonardo-mxln/stellartale.git`
2. Abra a pasta do projeto no **VS Code**.
3. Inicie a extensão **Live Server** no arquivo `index.html`.

---

## ✒️ Licença e Créditos

Desenvolvido por **Leonardo** como o arquivo e enciclopédia oficial do universo **StellarTale**. Todos os direitos do universo narrativo reservados.
