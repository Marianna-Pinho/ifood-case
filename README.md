# Sistema de Recomendação para Otimização da Distribuição de Cupons e Ofertas aos Clientes do iFood

O direcionamento das **ofertas corretas** para os **clientes corretos** na **hora certa** traz grandes impactos para um negócio, uma vez que pode otimizar o uso de recuros, mas, principalmente, fortalecer o engajamento e relacionamento de longo prazo com os clientes.

Existem diferentes formas de endereçarmos e modelarmos esse desafio. Em nossa resolução, utilizamos uma abordagem de Sistemas de Recomendação, os quais são amplamente utilizados por grandes empresas como Amazon e Netflix.

Neste README, você encontra as instruções para executar os códigos, assim como uma explicação dos arquivos e estrutura de pastas.

## 🗂️ Estrutura do Repositório

O repositório possui a seguinte estrutura de arquivos:

```
ifood-case/
├─ data/
│  ├─ raw/                      # conjunto de dados originais
│  └─ processed/                # dados prontos p/ modelagem
├─ models/                      # pesos dos modelos treinados
├─ notebooks/
│  ├─ 1_data_processing.ipynb   # processamento e EDA
│  ├─ 2_modeling.ipynb          # treinamento e avaliação dos modelos
├─ src/                         # código fonte (opcional)
├─ presentation/                # slides para stakeholders
├─ requirements.txt
└─ README.md
```

## ⚙️ Ambiente

Para executar o projeto, primeiro você precisa instalar as dependências. Recomendamos criar um ambiente virtual, para isolar as dependências deste projeto das de outros.

### Dependências
Estamos trabalhando com Python e ambiente virtual venv. Fique à vontade para utilizar o módulo ou gerenciador de ambientes virtuais de sua escolha. 

Para criação do ambiente virtual e instalação das dependências, execute os comandos abaixo.

```bash
# Linux
python -m venv .venv
source .venv/bin/activate  #no windows source .venv/Scripts/activate

pip install --upgrade pip
pip install -r requirements.txt
```

### Execução
Uma vez com o ambiente virtual criado e todas as dependências instaladas, você pode inicializar o servidor do Jupyter, através dos comandos:

```bash
jupyter lab
# ou
jupyter notebook
```
Uma vez que o servidor esteja em execução, ele vai disponibilizar uma URL como a do exemplo. 
- Você pode clicar sobre ela para abrir o workspace do Jupyter no seu navegador.
- Ou, se estiver utilizando VSCode, pode copiá-la e aplicá-la na opção **selecionar kernel** no canto superior direito, quando abrir um arquivo .ipynb.

```bash
# exemplo de url
http://127.0.0.1:8888/lab?token=XXXX
```

A partir de então, pode começar a experimentar os notebooks localizados no diretório ```notebooks/```.

## 🧹 ETL e Features

Para processar os dados e executar a análise exploratória, você pode utilizar o notebook [```ifood-case/notebooks/1_data_processing.ipynb```](https://github.com/Marianna-Pinho/ifood-case/blob/main/notebooks/1_data_processing.ipynb).

Ele vai carregar os dados disponibilizados em [```ifood-case/data/raw/```](https://github.com/Marianna-Pinho/ifood-case/tree/main/data/raw) e salvar os dados processados em [```ifood-case/data/processed/```](https://github.com/Marianna-Pinho/ifood-case/tree/main/data/processed).

## 🤖 Treino, Recomendação e Avaliação

Para executar o treinamento e avaliação do modelo de recomendação, você pode utilizar o notebook [```ifood-case/notebooks/2_modeling.ipynb```](https://github.com/Marianna-Pinho/ifood-case/blob/main/notebooks/2_modeling.ipynb).

- Ele vai carregar os dados salvos em [```ifood-case/data/processed/```](https://github.com/Marianna-Pinho/ifood-case/tree/main/data/processed).
- Vai salvar os splits de treinamento e teste, assim como os resultados das predições, também em [```ifood-case/data/processed/```](https://github.com/Marianna-Pinho/ifood-case/tree/main/data/processed).
- Vai salvar o modelo treinado em [```ifood-case/models/```](https://github.com/Marianna-Pinho/ifood-case/tree/main/models) e se necessário vai carregá-lo para execução das avaliações.

O armazenamento dos splits, modelos e resultados é opcional e você pode escolher não executá-los quando estiver experimentando o notebook.