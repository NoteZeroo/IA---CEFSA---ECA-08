# Projeto: [Agente Inteligente para Parkinson]

### 1. Identificação do Grupo
* **Instituição:** Centro Educacional Fundação Salvador Arena(CEFSA)
* **Curso:** ECA 08
* **Grupo:** 08
* **Integrantes:** * Leonardo Rodolfo Bortoluci - RA: 062220014
    * Júlia Rodrigues Lima - RA: 062220026
    * Gustavo Florêncio Simião - RA: 061230041

---

### 2. Área Problema Selecionada
Selecione a trilha tecnológica do projeto (marque com um [x]):
* [x] **Saúde 4.0:** Robótica Assistiva (Controladores Inteligentes/Fuzzy)
* [ ] **Smart Grid:** Eficiência Energética e Descarbonização
* [ ] **Agtech:** Automação de Precisão e Visão Computacional
* [ ] **Logística Autônoma:** Coordenação de AGVs e Otimização de Rotas

---

### 3. Diagnóstico e Definição do Agente
Nesta seção, descrevemos o cenário de atuação e a modelagem do agente inteligente.

* **Contexto:** A Saúde 4.0 é a aplicação de tecnologias digitais avançadas — como inteligência artificial, internet das coisas (IoT), big data e telemedicina — no setor da saúde para tornar o atendimento mais eficiente, personalizado e preventivo. Nesse modelo, dispositivos conectados monitoram pacientes em tempo real, dados são analisados para prever doenças e apoiar diagnósticos, e o cuidado deixa de ser apenas reativo (tratar doenças) para se tornar preditivo e contínuo, melhorando a qualidade de vida e otimizando recursos dos sistemas de saúde..
* **Problema:** A Doença de Parkinson é uma doença neurológica progressiva que afeta principalmente o controle dos movimentos. Ela ocorre devido à degeneração de neurônios produtores de dopamina no cérebro. Devido à natureza não linear, dinâmica e incerta dos sistemas biomecânicos humanos, abordagens baseadas em controle clássico apresentam limitações significativas.
* **Impacto:** A aplicação de técnicas de Inteligência Artificial, como Redes Neurais e Lógica Fuzzy, possibilita maior robustez, adaptabilidade e personalização, resultando em melhor desempenho funcional e qualidade de vida do paciente.

#### Modelagem PEAS (Agente Inteligente)
| Componente | Descrição |
| :--- | :--- |
| **Performance (P)** | Reduzir o tremor com precisão, mantendo movimento voluntário, segurança, estabilidade e adaptação em tempo real. |
| **Ambiente (E)** | Corpo do paciente em ambientes reais e dinâmicos, com variações fisiológicas e interferências externas.|
| **Atuadores (A)** | Motores/servomotores controlados por sistema embarcado para aplicar torque compensatório com segurança. |
| **Sensores (S)** | EMG, IMU, encoders e sensores de torque/corrente para detectar intenção, tremor e garantir controle em malha fechada. |

---

### 4. Arquitetura de Dados e IA

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


---

### 5. Plano de Tratamento de Dados (ETL)
O fluxo de processamento dos dados segue estas etapas:
1. **Extração:** Coleta de dados via arquivos Parkinsson disease.csv ou simulação.
2. **Transformação:** Limpeza de nulos, normalização e engenharia de atributos.
3. **Carga:** Disponibilização dos dados para o treinamento do modelo de IA.

---

### 6. Estrutura do Repositório
Organização simplificada para o Milestone 1:
* `/data`: Arquivos de dados originais (raw) e tratados (processed).
* `/notebooks`: Experimentos iniciais e análise exploratória.
* `/scripts`: Códigos Python (.py) contendo a lógica do agente e do ETL.
* `requirements.txt`: Lista de bibliotecas para rodar o projeto.
* `README.md`: Documentação atual do projeto.

---

### 7\. Abordagem escolhida
Optamos pelas Redes Neurais Artificiais devido à sua robustez no processamento de sinais biomecânicos não lineares. A RNA permite que o agente aprenda a relação entre a intenção muscular e o tremor físico, entregando uma compensação de torque personalizada e adaptável à progressão da doença, conforme os requisitos de segurança e funcionalidade do projeto.
<img width="856" height="460" alt="image" src="https://github.com/user-attachments/assets/b5529730-cb27-4c37-948c-4df35300ac7a" />

\---
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
* **Acesso à API:** Caso receba erro de "403 Forbidden", verifique se sua API Key está ativa e se o modelo `gemini-1.5-flash` está disponível na sua região.
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
