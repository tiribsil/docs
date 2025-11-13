# Projeto UFSKernel - Documentação

![Compilar Documentação LaTeX](https://github.com/UFSKernel/docs/actions/workflows/compile-latex.yml/badge.svg)
[![Latest Documentation PDF](https://img.shields.io/badge/PDF-Documentação_Mais_Recente-blue)](https://github.com/UFSKernel/docs/releases/latest)

Este repositório centraliza toda a documentação técnica do projeto UFSKernel. O documento é escrito de forma colaborativa em LaTeX e compilado automaticamente via GitHub Actions.

## Visualizando a Documentação

Você não precisa ter LaTeX instalado para ler a documentação! O PDF mais recente está sempre disponível para download em nossa página de Releases.

**➡️ [Baixar a versão mais recente do PDF](https://github.com/UFSKernel/docs/releases/latest)**

## Como Contribuir

A contribuição para a documentação segue um fluxo de trabalho específico, utilizando o [**Overleaf**](https://www.overleaf.com) para a edição do texto e o **Git/GitHub** para a submissão.

### Parte 1: Escrevendo seu Capítulo no Overleaf

1.  **Baixe o Template:** Faça o download do arquivo [`template_ufskernel.zip`](./template_ufskernel.zip), que está na raiz deste repositório.

2.  **Importe no Overleaf:** Crie um "New Project" no [Overleaf](https://www.overleaf.com) e escolha a opção "Upload Project". Envie o arquivo `.zip` que você baixou.

3.  **Escreva seu Capítulo:**
    - **Atenção:** Edite o arquivo `capitulos/template_capitulo.tex`.
    - Siga a estrutura de seções definida no template, respondendo todas as perguntas comentadas.
    - Use o comando `\cite{chave}` para referenciar as fontes do arquivo `referencias.bib`.
    - Caso queria adicionar uma bibliografia nova para citação, adicione o registro em `referencias.bib`.

### Parte 2: Submetendo sua Contribuição no GitHub

Quando seu capítulo estiver pronto, siga os passos abaixo para enviá-lo.

1.  **Fork e Clone:** Faça um fork desse repositório e clone-o. Crie uma nova branch para sua contribuição.

2.  **Baixe seu Capítulo do Overleaf:** No Overleaf, selecione o arquivo `capitulos/template_capitulo.tex` e faça o download dele para o seu computador.

3.  **Renomeie o Arquivo:** Renomeie o arquivo baixado seguindo o padrão `XX_<nome_do_capitulo>.tex`.
    - `XX` é um número de dois dígitos para definir a ordem. Verifique o último número usado na pasta `latex/capitulos/` e use o próximo.
    - `<nome_do_capitulo>` deve ser um nome curto e descritivo em minúsculas.

4.  **Mova o Arquivo:** Coloque o seu arquivo `.tex` renomeado dentro da pasta `latex/capitulos/` do seu clone local.

5.  **Atualize `main.tex`:** Abra o arquivo `latex/main.tex` e adicione a linha para incluir seu novo capítulo, na ordem correta:
    ```latex
    % ...
    \include{capitulos/00_infraestrutura_base}
    % outros includes...
    \include{capitulos/XX_<nome_do_capitulo>} % <-- ADICIONE SUA LINHA AQUI
    % ...
    ```

6. **Atualize `referencias.bib` (opcional):** Caso tenha adicionado um registro novo da bibliografia no seu projeto do Overleaf, também adicione-o no seu fork.

7.  **Faça o Commit e o Pull Request:** Adicione suas mudanças, faça o commit e envie para o seu fork. Em seguida, abra um Pull Request para a branch `main` do repositório `UFSKernel/docs`.

## Automação da Compilação (CI)

Este repositório utiliza **GitHub Actions** para compilar o documento LaTeX automaticamente a cada Pull Request.
- O workflow verifica se o documento compila sem erros.
- Se a compilação falhar, o botão **"Merge" do Pull Request será bloqueado**.
- Quando um PR é aprovado e mesclado, a Action executa novamente e atualiza o PDF na [página de Releases](https://github.com/UFSKernel/docs/releases/latest).

## Licença

A documentação deste projeto é licenciada sob a **Creative Commons Legal Code (CC0 1.0 Universal)**. Veja o arquivo `LICENSE` para mais detalhes.
