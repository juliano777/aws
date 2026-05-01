# AWS Machine Learning

A AWS oferece um amplo portfólio de serviços de **Machine Learning (ML)**, abrangendo desde soluções prontas para uso, até frameworks e ferramentas para cientistas de dados e desenvolvedores que desejam criar, treinar e implantar modelos de ML.

## Categorias de Serviços

### 1. Serviços de ML Pré-Treinados (AI Services)
Serviços prontos para uso que permitem adicionar inteligência a aplicações sem precisar treinar modelos:

- **Amazon Rekognition** → Análise de imagens e vídeos (detecção de objetos, rostos, texto, etc.)
- **Amazon Comprehend** → Processamento de linguagem natural (NLP) para análise de sentimentos, extração de entidades e tópicos.
- **Amazon Polly** → Conversão de texto em fala natural.
- **Amazon Transcribe** → Transcrição automática de fala para texto.
- **Amazon Translate** → Tradução automática de idiomas.
- **Amazon Lex** → Construção de chatbots e assistentes virtuais (mesma tecnologia da Alexa).
- **Amazon Textract** → Extração de texto e dados de documentos digitalizados.
- **Amazon Fraud Detector** → Detecção de fraudes em tempo real.
- **Amazon Personalize** → Sistemas de recomendação personalizados (semelhante à tecnologia da Amazon.com).
- **Amazon Kendra** → Busca corporativa inteligente.
- **Amazon Bedrock** → Acesso a modelos de *Foundation Models* (FM) via API, para criar apps de IA generativa sem precisar treinar modelos.
- **Amazon CodeWhisperer** → Geração de código assistida por IA.

### 2. Plataforma de Machine Learning (ML Services)
Serviços para treinar, ajustar e implantar modelos:

- **Amazon SageMaker**  
  - Serviço completo para cientistas de dados e desenvolvedores.
  - Oferece ferramentas para:
    - Preparação de dados
    - Treinamento e ajuste de modelos
    - Implantação em produção
    - Monitoramento de desempenho
  - Inclui módulos como **SageMaker Studio**, **SageMaker Autopilot** e **SageMaker Ground Truth**.

### 3. Frameworks e Infraestrutura (ML Frameworks & Infrastructure)
Ferramentas e frameworks open source disponíveis na AWS:

- **Frameworks suportados**: TensorFlow, PyTorch, MXNet, Scikit-learn, entre outros.
- **Infraestrutura otimizada**:
  - Instâncias **EC2 P4, P5, Inf1, Trn1** (com GPUs e chips AWS Trainium/Inferentia).
  - **AWS Trainium** → Chip customizado para treinamento de modelos.
  - **AWS Inferentia** → Chip para inferência otimizada de ML.

## Tabela Resumida dos Principais Serviços

| Categoria                  | Serviço / Produto       | Função Principal |
|----------------------------|-------------------------|------------------|
| **AI Services**            | Rekognition             | Análise de imagens e vídeos |
|                            | Comprehend              | NLP e análise de texto |
|                            | Polly                   | Texto para fala |
|                            | Transcribe              | Fala para texto |
|                            | Translate               | Tradução automática |
|                            | Lex                     | Chatbots e assistentes virtuais |
|                            | Textract                | Extração de dados de documentos |
|                            | Fraud Detector          | Detecção de fraudes |
|                            | Personalize             | Recomendação personalizada |
|                            | Kendra                  | Busca inteligente |
|                            | Bedrock                 | Modelos de IA generativa |
|                            | CodeWhisperer           | Geração de código com IA |
| **ML Services**            | SageMaker               | Treinamento, ajuste e implantação de modelos |
| **Frameworks & Infra**     | TensorFlow, PyTorch etc | Desenvolvimento de modelos |
|                            | Trainium / Inferentia   | Hardware otimizado para ML |

---

## Casos de Uso Comuns
- **Visão Computacional**: detecção de objetos, controle de qualidade em fábricas, análise de vídeos de segurança.
- **Processamento de Linguagem Natural**: análise de sentimentos, chatbots, pesquisa inteligente.
- **Recomendações**: e-commerce, streaming, personalização de conteúdo.
- **Automação de Documentos**: extração de informações de notas fiscais, contratos e PDFs.
- **IA Generativa**: criação de textos, imagens, código e assistentes virtuais.
