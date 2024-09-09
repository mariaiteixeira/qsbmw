# Projeto QuickSight - Dataset de carros vendidos da BMW em um modelo B2B

Este é um mini-projeto utilizando a solução **QuickSight** da AWS, para visualização de dados em modelos de Business Intelligence. 

<div align='center' style='display: inline_block'><img src="https://i.imgur.com/sF0gMy3.gif" alt="Gif do Dashboard feito no QuickSight, contendo diversos gráficos, porém com as cores diferentes"></div>

<details>
Versão 1:
<div align='center' style='display: inline_block'><img src="https://i.imgur.com/SQo5asJ.gif" alt="Gif do Dashboard feito no QuickSight, contendo diversos gráficos"></div>
</details>

## Sobre o projeto
Este projeto foi inspirado no vídeo da [Tech With Lucy](https://www.youtube.com/watch?v=4-8cXuZzKTg&ab_channel=TechWithLucy), em que é explicado como usar o QuickSight e como utilizar os dados salvos em buckets do S3 com o `manifest.json`. Com o `manifest.json` é possível fazer a relação direta do `.csv` utilizado e salvo no S3.

O formato do `manifest.json` é, comumente, este, de acordo com a documentação:

<details>
  
```
{
    "fileLocations": [
        {
            "URIs": [
                "uri1",
                "uri2",
                "uri3"
            ]
        },
        {
            "URIPrefixes": [
                "prefix1",
                "prefix2",
                "prefix3"
            ]
        }
    ],
    "globalUploadSettings": {
        "format": "JSON",
        "delimiter": ",",
        "textqualifier": "'",
        "containsHeader": "true"
    }
}
```
</details>

E você poderá ler mais sobre o assunto [aqui](https://docs.aws.amazon.com/quicksight/latest/user/supported-manifest-file-format.html). O arquivo editado que foi utilizado para a visualização está aqui no repositório.

Ao importar o JSON, o QuickSight importou os dados no estilo **SPICE**. **SPICE** significa Super-fast, Parallel, In-memory Calculation Engine. Ao invés de usar consultas com o SQL, o SPICE usa uma robusta memória e processa os dados de forma mais rápida, eficiente e útil para análises. Você pode ler mais [aqui](https://docs.aws.amazon.com/quicksight/latest/user/spice.html).

Um fato curioso foi uma limitação do QuickSight — para o scatterplot só foi carregado até 2500 data points. No dataset havia quase 5k entradas.

Abaixo, uma captura de tela de como ficou meu bucket no S3:

<div align='center' style='display: inline_block'><img src="https://i.imgur.com/5YCNJZe.png" alt="Print dos dois objetos no bucket do S3: o dataset e o manifest"></div>

E o dataset está disponível [neste link](https://www.kaggle.com/datasets/danielkyrka/bmw-pricing-challenge/data).

## Ao longo do projeto, as seguintes habilidades foram desenvolvidas:
- Uso de buckets no S3;
- Criação do `manifest.json`;
- Uso do QuickSight;
- Análise de Dados;
- Visualização de Dados (Data Visualization, DataViz).

## Tecnologias utilizadas neste projeto:
<img height="20" src="https://img.shields.io/badge/AWS%20S3-darkgreen"> <img height="20" src="https://img.shields.io/badge/AWS%20QuickSight-blue"> <img height="20" src="https://img.shields.io/badge/JSON-orange">

## Como reproduzir este repositório?
* Você pode fazer um `git clone` do repositório para a sua máquina, deste modo:

```
git clone https://github.com/mariaiteixeira/qsbmw.git
```

Após isso, o ideal é montar o projeto na nuvem AWS, pois as ferramentas em sua maioria foram utilizadas por lá.

## Licença
[![GPLv3 license](https://img.shields.io/badge/License-GPLv3-blue.svg)](http://perso.crans.org/besson/LICENSE.html)

## Status
<img src="https://img.shields.io/badge/Status-Finalizado-brightgreen">
