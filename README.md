*RPA Formulario*

# Automação de Download e Leitura de Planilha Excel com Power Automate Desktop

Este projeto automatiza o download de uma planilha Excel de um site específico, realiza a leitura dos dados e prepara o ambiente para a execução de um fluxo de trabalho.

## Visão Geral

O script Power Automate Desktop é dividido em três partes principais:

1.  **`VariaveisGlobais`**: Inicialização das variáveis globais necessárias para o fluxo.
2.  **`PreparacaoAmbiente`**: Limpeza do ambiente de trabalho, removendo arquivos Excel antigos.
3.  **`Planilha`**: Automação do download da planilha e leitura dos dados.

## Requisitos

* Power Automate Desktop instalado.
* Acesso à internet.
* Acesso a um serviço web Azure Logic Apps para obter a URL do site.

## Configuração

1.  **Azure Logic Apps**: Configure um serviço web Azure Logic Apps que retorne a URL do site desejado.
2.  **Power Automate Desktop**:
    * Importe o fluxo `main.xaml` para o Power Automate Desktop.
    * Certifique-se de que as variáveis `URLSite` e `PastaDownload` estejam configuradas corretamente.
    * Verifique se os seletores de interface do usuário no repositório de controles (`ControlRepository`) correspondem à estrutura do site.

## Execução

1.  Abra o Power Automate Desktop.
2.  Selecione o fluxo `main.xaml`.
3.  Clique em "Executar".

## Detalhes Técnicos

### `VariaveisGlobais`

* Obtém a URL do site do Azure Logic Apps.
* Obtém o caminho da pasta de downloads do usuário.
* Encerra o processo do Chrome, se estiver em execução.

### `PreparacaoAmbiente`

* Lista todos os arquivos Excel na pasta de downloads.
* Exclui arquivos Excel antigos que contenham a palavra "challenge" no nome.

### `Planilha`

* Abre o site no Chrome e baixa a planilha Excel.
* Lê os dados da planilha usando uma consulta SQL.
* Armazena os dados em uma variável para processamento posterior.

### `ControlRepository`

* Define os seletores e atributos dos elementos da interface do usuário.
* Utiliza o protocolo de automação `uia3`.
