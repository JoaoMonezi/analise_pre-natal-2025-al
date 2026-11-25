# Desigualdades no pré-natal em Alagoas em 2025

Projeto AB2 de **Introdução à Ciência de Dados**, curso de Inteligência Artificial, Instituto de Computação da UFAL. Docente Profª Cristina Tenório.

O estudo investiga como a frequência de menos de sete consultas de pré-natal varia entre grupos maternos e municípios de Alagoas. Também avalia um modelo de risco e o resultado de usar suas probabilidades para emitir alertas.

| Material | Acesso |
| --- | --- |
| Apresentação interativa | [Abrir no GitHub Pages](https://joaomonezi.github.io/analise_pre-natal-2025-al/) |
| Análise e código | [Notebook consolidado](notebooks/analise-sinasc-al-2025.ipynb) |
| Relatório da entrega | [Ler em Markdown](docs/relatorio.md) |

## Perguntas do projeto

1. Como escolaridade, raça/cor e faixa etária da mãe se associam à proporção de nascidos vivos com menos de sete consultas?
2. Como essa proporção varia entre os municípios e de que maneira a contagem absoluta distorce a comparação?
3. O perfil da mãe e o município onde ela mora ajudam a prever menos de sete consultas de pré-natal? Quando usamos essa previsão para gerar alertas, quantos casos reais identificamos e quantos alertas são falsos?

## Principais resultados

- **Perfil materno.** A escolaridade apresentou o contraste mais marcado na frequência de menos de sete consultas.
- **Municípios.** A contagem absoluta informa o volume de casos. A proporção permite comparar municípios com diferentes números de nascimentos.
- **Modelo preditivo.** A inclusão do município elevou a ROC-AUC de **0,6193** para **0,6819** na validação. A regressão logística 4a ficou perto de **0,70** nos dois testes e sinalizou **85% a 86%** dos casos reais com o limiar de **11,88%**. Cerca de **21% a 24%** dos alertas correspondiam a casos reais.

O indicador descreve a frequência registrada de consultas. A interpretação da qualidade clínica requer outras informações.

## Como reproduzir

O notebook contém resultados agregados e gráficos consultáveis no GitHub. Para reexecutá-lo, use Python 3.14 e instale as dependências a partir da raiz do repositório.

```sh
python -m pip install -r notebooks/requirements.txt
```

Coloque os três insumos da entrega na pasta local `Dados/Brutos/`:

- `SINASC_AL_2025_residencia.csv`
- `SINASC_AL_2026_2a_previa_residencia.csv`
- `IBGE_municipios_Alagoas.json`

Os microdados do SINASC/DATASUS e o cadastro do IBGE são insumos externos a este repositório. Use as mesmas extrações da entrega para reproduzir os números. Se estiverem em outro diretório, defina a variável `AB2_INPUT_DIR` com o caminho para ele.

Abra o notebook, selecione o ambiente Python com as dependências e execute todas as células em ordem. O processamento gera as bases tratadas, tabelas e gráficos em `Saídas do notebook/`. Para direcionar os resultados para outra pasta, defina `AB2_OUTPUT_DIR`.

## Equipe

Emerson Ferreira Barros · Pedro Lucas Leite da Silva · Weverton Deyvison da Silva · Diego Matheus Bastos de Oliveira · Joao Marcos de Lima Monezi.
