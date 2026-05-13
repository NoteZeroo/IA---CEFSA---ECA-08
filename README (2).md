# Projeto: Saúde 4.0: Robótica Assistiva

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Google Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&color=525252)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Gemini API](https://img.shields.io/badge/Gemini%20API-8E75B2?style=for-the-badge&logo=googlebard&logoColor=white)

### 🎥 Demonstração do Projeto
**[Assista ao Pitch e Demonstração da Solução (2-3 min)](https://youtu.be/9pO0D3D_aMs?si=YkmkrThsVTnbqILd)**

### 1. Identificação do Grupo

* **Instituição:** Faculdade Enhenheiro Salvador Arena (FESA)
* **Curso:** Engenharia de Controle e Automação
* **Grupo:** Grupo 8
* **Integrantes:**
  * Júlia Rodrigues Lima - RA: 062220026
  * Gustavo Florencio Simeão - RA: 061230041
  * Leonardo Rodolfo Bortoluci - RA: 062220014

\---

### 2\. Área Problema Selecionada

Selecione a trilha tecnológica do projeto (marque com um \[x]):

* \[x] **Saúde 4.0:** Robótica Assistiva (Controladores Inteligentes/Fuzzy)
* \[ ] **Smart Grid:** Eficiência Energética e Descarbonização
* \[ ] **Agtech:** Automação de Precisão e Visão Computacional
* \[ ] **Logística Autônoma:** Coordenação de AGVs e Otimização de Rotas

\---

### 3\. Diagnóstico e Definição do Agente

Nesta seção, descrevemos o cenário de atuação e a modelagem do agente inteligente.

* **Contexto:** A saúde 4.0 é a aplicação das tecnologias da Indústria 4.0 no setor da saúde, integrando Inteligência Artificial, Internet das Coisas, Big Data e computação em nuvem para tornar o cuidado mais conectado, eficiente e personalizado. Nesse modelo, dados dos pacientes são coletados e analisados em tempo real, permitindo monitoramento contínuo, diagnósticos mais precisos e tratamentos individualizados, inclusive em doenças como a Doença de Parkinson. Além disso, a saúde 4.0 amplia o uso da telemedicina, melhora a integração entre sistemas de saúde e otimiza a gestão hospitalar, tornando o atendimento mais proativo e centrado no paciente, embora traga desafios relacionados à segurança e privacidade dos dados.
* **Problema:** A Doença de Parkinson é uma doença neurológica progressiva que afeta principalmente o controle dos movimentos. Ela ocorre devido à degeneração de neurônios produtores de dopamina no cérebro. 
Devido à natureza não linear, dinâmica e incerta dos sistemas biomecânicos humanos, abordagens baseadas em controle clássico apresentam limitações significativas.
* **Impacto:** redução significativa do tremor e na melhoria da qualidade de vida do paciente, permitindo maior autonomia em atividades do dia a dia como escrever, se alimentar e segurar objetos.

#### Modelagem PEAS (Agente Inteligente)

|Componente|Descrição|
|-|-|
|**Performance (P)**|Para que uma solução inteligente voltada a pacientes com Doença de Parkinson seja considerada bem-sucedida, o agente deve perseguir metas objetivas relacionadas à redução de sintomas, melhoria funcional e segurança clínica. A principal meta é reduzir significativamente a amplitude e a frequência do tremor sem prejudicar o movimento voluntário. Isso significa que o sistema deve ser capaz de identificar corretamente o tremor e aplicar compensação ativa apenas quando necessário. Um critério de sucesso mensurável seria, por exemplo, uma redução percentual consistente da amplitude do tremor medida por sensores inerciais, mantendo a fluidez do movimento intencional.|
|**Ambiente (E)**|O agente opera diretamente no corpo do paciente, por meio de um dispositivo vestível (como uma órtese ou exoesqueleto leve), geralmente aplicado em membros superiores como mão, punho ou braço. Esse ambiente é considerado um ambiente físico-biológico, pois envolve interação com o sistema neuromuscular humano, especialmente em condições como a Doença de Parkinson. Além disso, o agente também atua em um ambiente digital complementar, onde os dados coletados são processados, armazenados e analisados, podendo incluir sistemas embarcados e, em alguns casos, integração com plataformas de monitoramento clínico.|
|**Atuadores (A)**|O agente inteligente interage com o ambiente principalmente por meio de atuadores eletromecânicos, como motores ou servomotores acoplados a uma órtese ou exoesqueleto, que aplicam torque para compensar o tremor ou auxiliar o movimento.As decisões são executadas por um controlador embarcado (microcontrolador ou processador), que roda os algoritmos de IA e envia comandos aos motores. Esses comandos passam por um driver de potência, responsável por regular corrente e tensão com segurança.O sistema também utiliza feedback em malha fechada, com encoders e sensores de torque ou corrente, para garantir estabilidade e evitar sobrecompensação.|
|**Sensores (S)**|**Atividade muscular (intenção de movimento)** -Sensores Eletromiografia (EMG) de superfície - Permite diferenciar movimento voluntário de tremor. **Aceleração e frequência do tremor** -Unidade de Medição Inercial (IMU - acelerômetro + giroscópio) - Permite identificar padrão típico do tremor e medir sua intensidade. **Posição e velocidade angular do membro**-Giroscópio da IMU ou encoder no atuador - Necessário para aplicar compensação proporcional e estável.**Torque/força aplicada pelo atuador**-Sensor de torque ou corrente do motor - Garante controle seguro e evita sobrecompensação.|

\---

### 4\. Arquitetura de Dados e IA

Definição das fontes de dados e da inteligência por trás da solução.

* **Origem dos Dados:** [Parkinson Disease Detection]([https://www.kaggle.com/datasets/fatemehmohammadinia/heart-attack-dataset-tarik-a-rashid](https://www.kaggle.com/datasets/debasisdotcom/parkinson-disease-detection)).
* **Lógica de IA:** Controladores Inteligentes/Fuzzy.
* **Justificativa:** Essa técnica — combinando Redes Neurais e controle inteligente — é ideal para esse problema porque a Doença de Parkinson envolve sinais motores altamente não lineares, variáveis e cheios de ruído, o que dificulta o uso de métodos tradicionais com parâmetros fixos. As Redes Neurais conseguem aprender padrões complexos dos sinais (como diferenciar tremor de movimento voluntário), enquanto técnicas como Lógica Fuzzy ou controle adaptativo permitem gerar respostas suaves e graduais, mais próximas do comportamento humano. Além disso, essas abordagens se adaptam ao paciente ao longo do tempo, acompanhando a progressão da doença, o que torna o sistema mais robusto, personalizado e eficaz em situações reais.
### 4.1\. Arquitetura Lógica (Lógica Fuzzy)

A inteligência do agente baseia-se em um Sistema de Inferência Fuzzy (Mamdani), que traduz sinais biométricos imprecisos em decisões de controle graduais.

* **Funções de Pertinência:** As variáveis de entrada e saída são mapeadas em conjuntos nebulosos através de funções triangulares ($trimf$):
  * **Entradas (Antecedentes):**
    * **Jitter (Variabilidade de Frequência):** Define a instabilidade do sinal motor.
    * Baixo: [0, 0, 0.005]
    * Alto: [0.004, 0.02, 0.02]
 
    * **PPE (Entropia de Percepção do Período):** Mede a desordem e complexidade dos sinais.
    * Estável: [0, 0, 0.25]
    * Crítico: [0.2, 0.5, 0.5]
  * **Saída (Consequente):**  
    * **Risco de Tremor/Crise:** Determina a intensidade da intervenção.
    * Monitoramento: [0, 0, 50]
    * Atenção: [30, 70, 100]
    * Urgente: [60, 100, 100]
 * **Regras de Inferência** O comportamento do robô é regido pelas seguintes sentenças lógicas:
1. **SE** (Jitter é Alto) OU (PPE é Crítico), **ENTÃO** Risco é Urgente.
2. **SE** (Jitter é Baixo) E (PPE é Estável), **ENTÃO** Risco é Monitoramento.

\---

### 5\. Plano de Tratamento de Dados (ETL)

O fluxo de processamento dos dados segue estas etapas:

1. **Extração:** Leitura automatizada do arquivo `Parkinsson disease.csv`via biblioteca Pandas.
2. **Transformação:** Limpeza de nulos, normalização e engenharia de atributos.
3. **Carga:** Disponibilização dos dados para o treinamento do modelo de IA.

\---
### 6. Evidências Visuais e Desempenho
*Arquivos armazenados na pasta `/assets/images`.*

**Imagem 1: [Interface de Logs do Sistema de Monitoramento]**
[Demonstra a execução em tempo real do sistema, exibindo a identificação de biomarcadores (frequência de tremor e congelamento de marcha), o cálculo da probabilidade de intervenção e a sugestão clínica gerada pela IA.]
![Logs do Sistema](assets/images/Captura de tela 2026-05-11 094359.png).

**Imagem 2: [Modelagem da rede Neural]**
[Demonstra o desempenho do modelo de Deep Learning na classificação dos estados do paciente, apresentando a precisão da rede em distinguir entre movimentos normais, tremores e episódios de "freezing".]
![Rede Neural](assets/images/Captura de tela 2026-05-11 100757.png).

**Imagem 3: [Predição e Análise interpretativa]**
[O gráfico demonstra a modelagem dos conjuntos nebulosos (Fuzzy) para as variáveis de entrada e saída do sistema. Ele define os níveis de intensidade (como "baixo", "médio" e "alto") para o tremor detectado e o torque de compensação, permitindo que o algoritmo tome decisões graduais e precisas em vez de apenas "ligado/desligado".]
![Visualização da Lógica Fuzzy](assets/images/Captura de tela 2026-05-11 104201.png).

**Imagem 4: [Resposta do Gemini a Predição]**
[Demonstra a resposta do Gemini]
![Resposta Gemini](assets/images/Captura de tela 2026-05-11 104201.png).

---
### 6.1\. Estrutura do Repositório

Organização simplificada para o Milestone 1:

* `/data`: Arquivos de dados originais (raw) e tratados (processed).
* `/notebooks`: Experimentos iniciais e análise exploratória.
* `/scripts`: Códigos Python (.py) contendo a lógica do agente e do ETL.
* `requirements.txt`: Lista de bibliotecas para rodar o projeto.
* `README.md`: Documentação atual do projeto.

---
### 7\. Abordagem escolhida
Optamos pelas Redes Neurais Artificiais devido à sua robustez no processamento de sinais biomecânicos não lineares. A RNA permite que o agente aprenda a relação entre a intenção muscular e o tremor físico, entregando uma compensação de torque personalizada e adaptável à progressão da doença, conforme os requisitos de segurança e funcionalidade do projeto.

<img width="857" height="371" alt="image" src="https://github.com/user-attachments/assets/58da24c8-156e-4fb4-ba05-7c9559162c8b" />

---
### 8\. Instruções para Execução
### 1. Preparação do Ambiente (Requirements)
Certifique-se de que as bibliotecas listadas no seu arquivo `requirements (2).txt` estão instaladas. Execute este comando na primeira célula:

```python
!pip install -q tensorflow google-generativeai scikit-fuzzy matplotlib numpy
```

### 2. Configuração da Inteligência Generativa
Para que a **Análise Interpretativa** (exigência do Milestone) funcione, você deve configurar a chave da API:
1.  Obtenha sua chave no [Google AI Studio](https://aistudio.google.com/).
2.  No código, localize e substitua o campo de configuração:
    ```python
    genai.configure(api_key="COLE_SUA_CHAVE_AQUI")
    # O modelo utilizado será o gemini-3-flash para maior rapidez
    ```

### 3. Fluxo de Execução do Agente
Execute as células na sequência abaixo para respeitar o ciclo de vida do agente inteligente:

* **Célula 1 - Importação e Dados:** Carrega o **TensorFlow** para a Rede Neural e simula os dados dos **Sensores (S)** definidos (EMG e IMU).
* **Célula 2 - Treinamento da RNA:** Define a arquitetura do "cérebro" do agente e inicia o aprendizado (`model.fit`).
    > **Nota de Desempenho:** Observe o gráfico de **Loss (Perda)**. Como critério de sucesso, a linha deve ser descendente, provando que o agente está aprendendo a prever o torque.
* **Célula 3 - Predição e Atuador (A):** Simula o processamento em tempo real. A rede recebe os sinais dos sensores e comanda o torque do motor, enviando o log para o **Gemini** gerar a explicação técnica.

### 4. Guia de Solução de Problemas (Troubleshooting)
* **Erro de Dimensão (Shape):** A Rede Neural espera 3 entradas (EMG, ACC, GYRO). Garanta que o array de entrada tenha o formato `(1, 3)`.
* **Acesso à API:** Caso receba erro de "403 Forbidden", verifique se sua API Key está ativa e se o modelo `gemini-3-flash` está disponível na sua região.
* **Runtime:** Se o código travar após a instalação das bibliotecas, clique em **"Ambiente de Execução" > "Reiniciar sessão"**.

### 5. Validação do Milestone 3
O grupo saberá que o objetivo foi atingido se:
1.  O gráfico mostrar a **evolução do aprendizado** (queda do erro).
2.  O sistema imprimir um valor de **Torque de Compensação** (ex: `1.2450 Nm`) condizente com a intensidade do tremor.
3.  O **Gemini** fornecer o diagnóstico teórico, explicando a relação entre o músculo e o motor.

Para reproduzir o ambiente e testar o diagnóstico:

1. Clone este repositório.
2. Instale as dependências:

```bash
   pip install -r requirements.txt
```

---

## 🤖 9. Apêndice de IA

Relato sobre o suporte de ferramentas de Inteligência Artificial Generativa no desenvolvimento:

* **Ferramentas:** Google Gemini (modelos 1.5-flash e 3-flash-preview): Utilizado como o motor central de Inteligência Artificial Explicável (XAI) integrado ao código.
* **Bibliotecas Python:** google-genai (SDK atualizado) para comunicação via API.
* **Aplicação:**
    * Estruturação do Código: Apoio na migração da biblioteca legada google-generativeai para a nova google-genai, garantindo a compatibilidade com o modelo mais recente.
    * Organização do Pipeline de ETL: Integração do fluxo de leitura do dataset real do Drive (Parkinsson disease.csv) com o tratamento de dados para alimentação da lógica Fuzzy.
    * Revisão Textual e Interpretação: Geração de análises clínicas automatizadas baseadas nos resultados técnicos (Jitter, PPE e Torque), traduzindo dados brutos de engenharia em justificativas fundamentadas para profissionais de saúde.
    * Tratamento de Exceções: Implementação de blocos try/catch para garantir a resiliência do sistema (Safe-Fail) em caso de falhas de rede ou ausência de dados.

* **Validação:**
    * Conferência Técnica: Todos os cálculos de torque gerados pelo motor Fuzzy e as predições de instabilidade foram validados manualmente pelo grupo para garantir que o atuador não ultrapassasse limites de segurança física.
    * Acurácia das Interpretações: As justificativas geradas pela IA foram revisadas para assegurar o uso correto dos termos técnicos (como "biomarcadores", "entropia de pitch" e "estabilidade cinemática") e a aderência aos objetivos da Saúde 4.0.
    * Estabilidade do Sistema: O pipeline foi testado de ponta a ponta, confirmando que a saída final (Relatório Técnico) reflete com precisão os dados coletados na etapa de diagnóstico. 

---
© 2026 - Projeto de Inteligência Artificial - Faculdade Engenheiro Salvador Arena
