# Tradutor Automático  Local ( Sem IA ) (v7.3 - Versão Final Consolidada)

Este script Python é uma ferramenta robusta para a tradução automática de textos, focada em arquivos de jogos Ren'Py (.rpy) e documentos Word (.docx). Ele foi desenvolvido com funcionalidades avançadas para preservar a integridade do código em arquivos Ren'Py e adaptar o estilo da tradução para o Português do Brasil (pt-BR), considerando formalidade e contexto.

**É importante notar que, embora esta seja uma versão "consolidada", a tradução automática, por sua natureza, sempre se beneficia de aprimoramentos contínuos e um refinamento manual para garantir a melhor qualidade e fluidez.**

## Funcionalidades Principais

* **Proteção de Código Ren'Py**: Preserva tags Ren'Py (`{...}`) e variáveis (`[...]`) durante o processo de tradução para evitar a corrupção do script do jogo.
* **Detecção de Diálogos e Narrações**: Identifica e traduz corretamente linhas de diálogo e narração em arquivos `.rpy`, mesmo em estruturas complexas com múltiplas expressões.
* **Lógica de Pareamento Flexível**: Implementa uma lógica avançada para parear linhas de tradução, garantindo que o texto original e o espaço para a tradução sejam corretamente associados.
* **Tradução de Arquivos `.docx`**: Permite a tradução de documentos Word, parágrafo por parágrafo.
* **Adaptação de Formalidade**: Analisa o texto em inglês para detectar o nível de formalidade e tenta adaptar a tradução para o Português do Brasil para um tom mais formal ou informal/gírias, conforme o contexto.
* **Correções Contextuais (pt-BR)**: Aplica um conjunto de regras de substituição pós-tradução para corrigir frases literais, gírias e expressões idiomáticas comuns em português, melhorando a naturalidade do texto traduzido.
* **Cache de Tradução (LRU Cache)**: Utiliza um cache para armazenar traduções de textos repetidos, otimizando o desempenho e evitando traduções redundantes.
* **Instalação Automática de Dependências**: Verifica e instala automaticamente as bibliotecas Python necessárias (`argostranslate` e `python-docx`) caso não estejam presentes.
* **Download Automático de Modelos de Idioma**: Tenta baixar e instalar os modelos de idioma do Argos Translate (`en` para `pt`) se eles não forem encontrados localmente.

## Dependências

Este script requer as seguintes bibliotecas Python:

* `argostranslate`: Para a funcionalidade de tradução automática.
* `python-docx`: Para a manipulação de arquivos `.docx`.

**A instalação dessas dependências é automatizada pelo script.** Se você executar o script e elas não estiverem presentes, ele tentará instalá-las automaticamente usando `pip`.

## Como Usar

O script é executado via linha de comando e requer dois argumentos principais: o `caminho` (diretório ou arquivo) e o `modo` de operação.

### Instalação e Execução (Primeira Vez)

1.  **Salve o script**: Salve o código Python fornecido (por exemplo, como `tradutor.py`).
2.  **Execute via terminal**: Abra um terminal ou prompt de comando e navegue até o diretório onde você salvou o script.

    ```bash
    # Para traduzir arquivos Ren'Py em uma pasta:
    python tradutor.py --modo rpy ./caminho/para/pasta_do_jogo

    # Para traduzir um único arquivo .docx:
    python tradutor.py --modo docx ./caminho/para/meu_documento.docx
    ```
    Na primeira execução, o script verificará e instalará as dependências e os modelos de idioma necessários. Isso pode levar alguns minutos, dependendo da sua conexão com a internet.

### Argumentos da Linha de Comando

* `caminho`:
    * No modo `rpy`: O caminho para a **pasta** que contém os arquivos `.rpy` a serem traduzidos.
    * No modo `docx`: O caminho completo para o **arquivo `.docx`** a ser traduzido.
* `--modo [rpy|docx]`:
    * `rpy`: Ativa o modo de tradução para arquivos Ren'Py.
    * `docx`: Ativa o modo de tradução para arquivos Word.

### Exemplos de Uso

1.  **Traduzir uma pasta de arquivos Ren'Py**:
    ```bash
    python tradutor.py --modo rpy "C:\Meus Jogos\MeuProjetoRenPy\game\scripts"
    ```
    (No Linux/macOS, use `/home/usuario/MeusJogos/MeuProjetoRenPy/game/scripts`)

2.  **Traduzir um documento Word**:
    ```bash
    python tradutor.py --modo docx "D:\Documentos\RelatorioOriginal.docx"
    ```

## Estrutura do Projeto (Assumindo `tradutor.py`)

( Detalhe: PB é a biblioteca Português Brasil, e não PT como normalmente é. Obrigado! )
