# Módulo 01 — Fundamentals of Machine Learning and Artificial Intelligence

---

## 📌 Introdução

Este módulo cobre os fundamentos de **Inteligência Artificial (IA)**, **Machine Learning (ML)**, **Deep Learning (DL)** e **IA Generativa**, além de apresentar os principais serviços AWS que utilizam essas tecnologias.

---

## 1. O Ecossistema da IA: Relação entre os Conceitos

Os quatro grandes conceitos formam uma hierarquia, onde cada um é um subconjunto do anterior:

```
┌──────────────────────────────────────┐
│         Inteligência Artificial (IA) │
│  ┌────────────────────────────────┐  │
│  │      Machine Learning (ML)     │  │
│  │  ┌──────────────────────────┐  │  │
│  │  │     Deep Learning (DL)   │  │  │
│  │  │  ┌────────────────────┐  │  │  │
│  │  │  │   IA Generativa    │  │  │  │
│  │  │  └────────────────────┘  │  │  │
│  │  └──────────────────────────┘  │  │
│  └────────────────────────────────┘  │
└──────────────────────────────────────┘
```

| Conceito | Definição | Exemplo |
|---|---|---|
| **IA** | Campo amplo que desenvolve sistemas capazes de realizar tarefas que exigem inteligência humana | Reconhecimento de voz, tomada de decisão |
| **ML** | Subconjunto da IA onde máquinas aprendem a partir de dados para melhorar seu desempenho | Detecção de spam em e-mails |
| **Deep Learning** | Subconjunto do ML baseado em redes neurais artificiais (inspiradas no cérebro humano) | Amazon Rekognition — análise de imagens |
| **IA Generativa** | Subconjunto do Deep Learning capaz de **criar novo conteúdo** (texto, imagens, código) sem retreinamento | ChatGPT, Claude, Stable Diffusion |

> **Ponto-chave:** IA Generativa **não precisa de retreinamento ou fine-tuning** para se adaptar — ela usa modelos de Deep Learning já existentes.

---

## 2. Fundamentos de Machine Learning

### 2.1 Dados de Treinamento

O processo de ML começa com os dados. Existe um princípio famoso: **"Garbage in, Garbage out"** — um modelo é tão bom quanto os dados usados para treiná-lo.

#### Dados Rotulados vs. Não Rotulados

| Tipo | Definição | Exemplo |
|---|---|---|
| **Labeled (Rotulado)** | Cada exemplo possui uma etiqueta/classificação associada | Imagens de gatos e cachorros **já identificadas** |
| **Unlabeled (Não Rotulado)** | Exemplos sem etiquetas, apenas os dados brutos | Coleção de imagens **sem classificação** |

#### Dados Estruturados vs. Não Estruturados

| Tipo | Subtipos | Exemplo |
|---|---|---|
| **Estruturado** | Tabular, Séries temporais | Planilha de vendas, cotações de ações |
| **Não Estruturado** | Texto, Imagem, Áudio, Vídeo | Posts de redes sociais, fotos, podcasts |

---

### 2.2 Tipos de Aprendizado (ML Process)

| Tipo | Como funciona | Exemplo de uso |
|---|---|---|
| **Supervised Learning** | Treina com dados **rotulados** | Classificar e-mails como spam ou não |
| **Unsupervised Learning** | Treina com dados **não rotulados**, buscando padrões | Agrupar clientes por comportamento de compra |
| **Reinforcement Learning** | Aprende por **recompensas e penalidades** | Carros autônomos, jogos (xadrez, Go) |

---

### 2.3 Inferência (Inferencing)

Após o treinamento, o modelo começa a fazer **previsões**. Isso se chama **inferência**.

| Tipo | Quando usar | Exemplo |
|---|---|---|
| **Batch Inferencing** | Quando a velocidade **não é crítica** — processa grandes volumes de uma vez | Análise de dados de vendas do mês |
| **Real-time Inferencing** | Quando a decisão precisa ser **imediata** | Chatbots, carros autônomos |

---

## 3. Fundamentos de Deep Learning

### 3.1 Redes Neurais

Redes neurais são a base do Deep Learning. Funcionam de forma análoga ao cérebro humano:

- **Neurônios** → **Nós (nodes)**
- **Sinapses** → **Conexões entre nós**
- **Camadas:** `Input Layer → Hidden Layers → Output Layer`

> **Como aprende:** O modelo recebe exemplos (ex: dados de clientes), ajusta as conexões entre os nós e, com o tempo, consegue identificar padrões em dados **nunca vistos antes**.

### 3.2 Aplicações de Deep Learning

| Área | O que faz | Serviço AWS |
|---|---|---|
| **Computer Vision** | Interpretação de imagens e vídeos — classificação, detecção de objetos | Amazon Rekognition |
| **NLP (Natural Language Processing)** | Processamento de linguagem humana — tradução, sentimentos, geração de texto | Amazon Comprehend, Lex |

---

## 4. Fundamentos de IA Generativa

### 4.1 Foundation Models (FMs)

**Foundation Models** são modelos pré-treinados em dados em escala da internet. A grande diferença em relação ao ML tradicional:

| ML Tradicional | Foundation Models |
|---|---|
| Um modelo por tarefa | Um único modelo para múltiplas tarefas |
| Requer dados rotulados | Treina com dados não rotulados (self-supervised) |
| Retreino completo para nova tarefa | Adaptável com prompt, fine-tuning ou RAG |

**Tarefas que um FM pode realizar:**
- Geração de texto
- Sumarização
- Extração de informação
- Geração de imagens
- Chatbot / Q&A

> **AWS Bedrock** oferece acesso a FMs de empresas como Anthropic (Claude), Meta, Mistral AI, Stability AI e Amazon Titan.

---

### 4.2 Ciclo de Vida de um Foundation Model

```
Data Selection → Pre-training → Optimization → Evaluation → Deployment → Feedback & Improvement
      ↑___________________________________________________________________|
```

| Fase | Descrição |
|---|---|
| **Data Selection** | Coleta de dados não rotulados em larga escala (texto, imagens, vídeos da internet) |
| **Pre-training** | Aprendizado auto-supervisionado — o modelo aprende contexto, significado e relações sem labels explícitas |
| **Continuous Pre-training** | Pré-treinamento adicional para expandir o conhecimento do modelo |
| **Optimization** | Refinamento via prompt engineering, RAG ou fine-tuning |
| **Evaluation** | Medição de desempenho com métricas e benchmarks |
| **Deployment** | Integração em aplicações, APIs ou sistemas |
| **Feedback & Improvement** | Monitoramento contínuo e iterações de melhoria |

---

### 4.3 Tipos de Foundation Models

#### 🔤 Large Language Models (LLMs)
- Arquitetura mais comum: **Transformer**
- Processam texto através de **tokens**, **embeddings** e **vetores**

| Conceito | O que é | Exemplo |
|---|---|---|
| **Token** | Unidade básica de texto | `"A"` `"puppy"` `"is"` `"to"` `"dog"` |
| **Embedding** | Representação numérica (vetor) de um token | Vetor de "cat" é próximo ao de "feline" e "kitten" |
| **Vetor** | Lista de números que captura significado e relações | Permite que o modelo entenda similaridade semântica |

#### 🖼️ Diffusion Models
Geram imagens a partir de ruído aleatório em duas etapas:

1. **Forward Diffusion:** Adiciona ruído progressivamente a uma imagem até só restar ruído
2. **Reverse Diffusion:** Remove o ruído gradualmente para gerar uma nova imagem

> **Exemplo famoso:** Stable Diffusion (geração de imagens a partir de texto)

#### 🔀 Multimodal Models
- Processam e geram **múltiplos tipos de dados simultaneamente** (texto + imagem, por exemplo)
- **Usos:** Legendagem automática de vídeos, geração de gráficos a partir de texto, Q&A visual

#### 🥊 GANs (Generative Adversarial Networks)
Dois modelos competindo entre si:

| Rede | Função |
|---|---|
| **Generator** | Gera dados sintéticos tentando enganar o discriminador |
| **Discriminator** | Tenta distinguir dados reais dos sintéticos |

> O treinamento continua até o gerador produzir dados **indistinguíveis dos reais**.

#### 🔢 VAEs (Variational Autoencoders)
Duas partes:

| Parte | Função |
|---|---|
| **Encoder** | Comprime os dados de entrada em um espaço latente (representação compacta) |
| **Decoder** | Reconstrói os dados originais a partir da representação compacta |

---

### 4.4 Técnicas de Otimização de FMs

| Técnica | O que faz | Altera pesos do modelo? | Custo/Complexidade |
|---|---|---|---|
| **Prompt Engineering** | Instrui o modelo via texto bem elaborado | ❌ Não | Baixo |
| **RAG** (Retrieval-Augmented Generation) | Recupera documentos relevantes e usa como contexto | ❌ Não | Médio |
| **Fine-tuning** | Adiciona datasets específicos ao modelo base | ✅ Sim | Alto |

#### Estrutura de um Prompt
```
[Instrução]   → Descreve o que o modelo deve fazer
[Contexto]    → Informação externa para guiar o modelo
[Input Data]  → Dado de entrada para o qual se quer resposta
[Output]      → Formato/tipo de saída esperada
```

**Exemplo de prompt:**
> *"Você é um jornalista experiente especialista em síntese. Resuma o texto a seguir em 2-3 frases: [texto longo aqui]"*

#### Fine-tuning: modalidades
- **Instruction fine-tuning:** Exemplos de como responder a instruções específicas
- **RLHF (Reinforcement Learning from Human Feedback):** Feedback humano para alinhar o modelo com preferências humanas

---

## 5. Infraestrutura e Serviços AWS de IA/ML

### 5.1 O Stack AWS de IA/ML

```
┌──────────────────────────────────────────────────────┐
│                   GENERATIVE AI                       │
│   SageMaker JumpStart | Amazon Bedrock | Amazon Q    │
├──────────────────────────────────────────────────────┤
│                  AI/ML SERVICES                       │
│  Comprehend | Translate | Textract | Lex | Polly     │
│  Transcribe | Rekognition | Kendra | Personalize     │
├──────────────────────────────────────────────────────┤
│                  ML FRAMEWORKS                        │
│              Amazon SageMaker AI                     │
└──────────────────────────────────────────────────────┘
```

---

### 5.2 Camada de ML Frameworks

#### 🧠 Amazon SageMaker AI
- Serviço totalmente gerenciado para **construir, treinar e implantar** modelos ML
- Oferece infraestrutura, ferramentas e workflows completos
- Reduz o esforço em cada etapa do ciclo de vida de ML

---

### 5.3 Camada de AI/ML Services

| Serviço | Domínio | O que faz |
|---|---|---|
| **Amazon Comprehend** | Texto/NLP | Extrai insights de texto: sentimento, entidades, idioma, tópicos |
| **Amazon Translate** | Texto | Tradução automática neural — precisa e natural |
| **Amazon Textract** | Documentos | Extrai texto e dados de documentos escaneados (vai além do OCR) |
| **Amazon Lex** | Chatbots | Cria interfaces conversacionais (voz e texto) — mesma tecnologia da Alexa |
| **Amazon Polly** | Fala | Converte texto em fala realista (text-to-speech) |
| **Amazon Transcribe** | Fala | Converte áudio em texto (speech-to-text) com timestamps |
| **Amazon Rekognition** | Visão | Análise de imagens e vídeos — detecta objetos, rostos, cenas, texto |
| **Amazon Kendra** | Busca | Busca inteligente em repositórios corporativos |
| **Amazon Personalize** | Recomendações | Recomendações personalizadas em tempo real |
| **AWS DeepRacer** | Educação/RL | Carro de corrida 1/18 para aprender Reinforcement Learning de forma prática |

---

### 5.4 Camada de Generative AI

| Serviço | O que faz |
|---|---|
| **Amazon SageMaker JumpStart** | Acelera o início com soluções pré-construídas e +150 modelos open-source com deploy em 1 clique |
| **Amazon Bedrock** | Acesso via API a FMs de várias empresas (Anthropic, Meta, Mistral, Stability AI, Amazon) — serverless |
| **Amazon Q** | Assistente generativo para uso corporativo — responde perguntas usando dados da empresa |
| **Amazon Q Developer** | Recomendações de código com ML para C#, Java, JavaScript, Python e TypeScript |

> **PartyRock:** Playground do Amazon Bedrock para experimentar IA Generativa sem necessidade de código.

---

### 5.5 Considerações de Custo

| Fator | Impacto no Custo |
|---|---|
| **Responsividade e Disponibilidade** | Maior disponibilidade (multi-região) = maior custo |
| **Redundância e Cobertura Regional** | Deploy em múltiplas AZs/Regiões = custo adicional |
| **Performance** | GPU e aceleradores customizados = mais caro, porém mais rápido |
| **Token-based Pricing** | Paga por tokens processados (ex: Bedrock, Amazon Q Developer) |
| **Provisioned Throughput** | Capacidade reservada (Polly, Transcribe) = custo maior, mas previsível |
| **Custom Models** | Treinar/implantar modelos próprios pode ter custo significativo |

> ⚖️ **Equilíbrio:** Avalie sempre custo × performance × disponibilidade conforme a necessidade do seu caso de uso.

---

## 🗂️ Resumo Visual do Módulo

```
IA → ML → Deep Learning → IA Generativa (hierarquia de conceitos)

Dados → Algoritmo → Treinamento → Inferência (processo de ML)

FM → Pré-treino → Otimização (Prompt/RAG/Fine-tuning) → Deploy (ciclo de vida)

AWS Stack: SageMaker AI → AI/ML Services → Generative AI (Bedrock, Q)
```

---

*Módulo 01 — AWS Machine Learning Foundations | Resumo gerado em: Setembro/2026*
