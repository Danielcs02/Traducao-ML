# Tradutor Personalizado com Hugging Face Transformers

Este projeto documenta o processo de criação e *fine-tuning* de modelos de tradução automática para os pares de línguas Inglês-Português e Português-Inglês. O objetivo foi especializar um modelo pré-treinado (`t5-small`) utilizando um dataset de sentenças do Tatoeba para obter traduções mais precisas e contextualizadas.

O treino foi realizado no Google Colab para aproveitar o poder das GPUs, e os modelos finais foram guardados no Hugging Face Hub para fácil acesso e utilização.

---

## 🚀 Funcionalidades

* **Fine-tuning** do modelo `t5-small` da Google.
* **Modelo de Tradução Inglês para Português (EN-PT)**.
* **Modelo de Tradução Português para Inglês (PT-EN)**.
* Pipeline de treino e pré-processamento de dados utilizando as bibliotecas `transformers` e `datasets`.
* Exemplos de como carregar e usar os modelos treinados para inferência.

---

## 🛠️ Tecnologias Utilizadas

* **Python 3.x**
* **PyTorch**
* **Hugging Face Transformers:** Para carregar, treinar e usar os modelos.
* **Hugging Face Datasets:** Para processar e preparar os dados.
* **Pandas:** Para a manipulação inicial dos dados.
* **UV:** Para gestão do ambiente virtual e instalação de pacotes.
* **Google Colab:** Para o treino acelerado com GPU.
* **VS Code:** Para o desenvolvimento e teste local.

---

## ⚙️ Configuração do Ambiente Local

Para executar os modelos localmente, siga estes passos:

1.  **Clone este repositório:**
    ```bash
    git clone <URL-DO-SEU-REPOSITORIO>
    cd <NOME-DA-PASTA-DO-REPOSITORIO>
    ```

2.  **Crie e ative um ambiente virtual com `uv`:**
    ```bash
    # Criar o ambiente
    uv venv

    # Ativar no Windows
    .\.venv\Scripts\activate

    # Ativar no Linux / macOS
    source .venv/bin/activate
    ```

3.  **Instale as dependências:**
    ```bash
    uv pip install -r requirements.txt
    ```

---

## 🤖 Como Usar os Modelos

Para usar um dos modelos treinados, você pode carregá-lo diretamente do Hugging Face Hub.

### Exemplo: Tradução de Inglês para Português

```python
from transformers import pipeline

model_id_en_pt = "Orpheus095/meu_modelo_tradutor"

# Carrega o modelo do Hub e cria o pipeline
translator = pipeline(task="translation_en_to_pt", model=model_id_en_pt)

# Prepara a frase com o prefixo correto
frase = "translate English to Portuguese: This is a test of my custom model."

# Faz a tradução
resultado = translator(frase)
print(f"Tradução: {resultado[0]['translation_text']}")
```

## 🧠 Modelos Treinados

Os modelos finais estão disponíveis no Hugging Face Hub:

* **Modelo EN-PT:** [huggingface.co/Orpheus_095/meu_modelo_tradutor](https://huggingface.co/SEU-NOME-DE-USUARIO/meu_modelo_tradutor)

## 🙏 Agradecimentos

* A base de dados de sentenças foi obtida do projeto **Tatoeba**, uma fonte incrível de dados linguísticos abertos.