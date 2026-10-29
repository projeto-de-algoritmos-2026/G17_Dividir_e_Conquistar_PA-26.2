<h1><font size="6"><b>Nome Projeto</b></font><br></h1>
<h3><b>Número da Lista:</b> 17<br></h3>
<h3><i>Conteúdo da disciplina:</i> Dividir e Conquistar<br></h3>
<h3>Alunos</h3>

| Matrícula | Aluno |
|-----------|----------------------------------|
| 251013660 | Matheus Moretti Soares           |
| 251019771 | Daniel Filipe Borges de Oliveira |

---

## Sobre
O **Detector de Similaridade Estrutural** é uma ferramenta web desenvolvida para identificar potenciais plágios ou cópias estruturais entre textos. Em vez de utilizar comparações simples de palavras-chave, o sistema analisa a ordem sequencial das ideias. 

A aplicação utiliza o algoritmo de **Counting Inversions (Merge Sort modificado)** para calcular a "distância de desordem" entre os textos. Quanto menor o número de inversões necessárias para realinhar os textos, maior a probabilidade de similaridade estrutural.

## Screenshots

## Instalação

Linguagem: Python e JavaScript
Framework: FastAPI

<font size = "5">**Pré-requisitos:** </font>
- Python 3.x instalado
- Git instalado

<font size = "5"> **Comandos necessários:**</font>

**1. Clone este repositório:**
```bash
git clone https://github.com/projeto-de-algoritmos-2026/G17_Dividir_e_Conquistar_PA-26.2.git

cd G17_Dividir_e_Conquistar_PA-26.2
```
**2. Crie e ative o ambiente virtual:**
```bash
python -m venv venv

# Ativar no Windows:
venv\Scripts\activate

# Ativar no Linux/Mac:
source venv/bin/activate
```

**3. Instale as dependências do backend:**
```bash
pip install -r backend/requirements.txt
```

## Uso
Com as dependências instaladas e o ambiente virtual ativo, inicie o servidor local executando:

```bash
uvicorn backend.main:app --reload
```

Após o servidor iniciar (rodando em http://localhost:8000), abra o arquivo frontend/index.html diretamente no seu navegador ou através da extensão Live Server da sua IDE para utilizar a aplicação.

## Outros
**Análise Algorítmica:** O núcleo matemático do projeto evita a contagem de força bruta $O(N^2)$ ao implementar o algoritmo de Merge Sort para a contagem de inversões. Isso reduz a complexidade de tempo da análise de similaridade para $O(N \log N)$, garantindo alta performance mesmo ao comparar redações longas.

**Arquitetura e Escalabilidade:**
Em um detector de plágio em escala real, a integração de um Banco de Dados não visa criar "inteligência" (no sentido de Machine Learning), mas atuar como um Repositório de Base (Corpus) e um Otimizador de Performance.

O escopo atual do projeto opera como uma API stateless (sem estado): ela recebe o Texto A e o Texto B, compara os dois simultaneamente, devolve o resultado e descarta os dados. Com a adição de um banco de dados, a arquitetura se tornaria stateful (com estado), permitindo comparações de 1 para N. Dessa forma, um único texto suspeito seria contrastado contra milhares de documentos pré-processados e em cache, viabilizando o armazenamento do histórico de plágios.