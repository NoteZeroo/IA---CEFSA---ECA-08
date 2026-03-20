# Projeto: [Agente Inteligente para Parkinson]

### 1. Identificação do Grupo
* **Instituição:** Centro Educacional Fundação Salvador Arena(CEFSA)
* **Curso:** [ECA 08]
* **Grupo:** [08]
* **Integrantes:** * [Leonardo Rodolfo Bortoluci] - RA: [062220014]
    * [Júlia Rodrigues Lima] - RA: [062220026]
    * [Gustavo Florêncio Simião] - RA: [061230041]

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

* **Contexto:** [A Saúde 4.0 é a aplicação de tecnologias digitais avançadas — como inteligência artificial, internet das coisas (IoT), big data e telemedicina — no setor da saúde para tornar o atendimento mais eficiente, personalizado e preventivo. Nesse modelo, dispositivos conectados monitoram pacientes em tempo real, dados são analisados para prever doenças e apoiar diagnósticos, e o cuidado deixa de ser apenas reativo (tratar doenças) para se tornar preditivo e contínuo, melhorando a qualidade de vida e otimizando recursos dos sistemas de saúde.].
* **Problema:** [A Doença de Parkinson é uma doença neurológica progressiva que afeta principalmente o controle dos movimentos. Ela ocorre devido à degeneração de neurônios produtores de dopamina no cérebro. Devido à natureza não linear, dinâmica e incerta dos sistemas biomecânicos humanos, abordagens baseadas em controle clássico apresentam limitações significativas.].
* **Impacto:** [A aplicação de técnicas de Inteligência Artificial, como Redes Neurais e Lógica Fuzzy, possibilita maior robustez, adaptabilidade e personalização, resultando em melhor desempenho funcional e qualidade de vida do paciente.].

#### Modelagem PEAS (Agente Inteligente)
| Componente | Descrição |
| :--- | :--- |
| **Performance (P)** | Reduzir o tremor com precisão, mantendo movimento voluntário, segurança, estabilidade e adaptação em tempo real. |
| **Ambiente (E)** | Corpo do paciente em ambientes reais e dinâmicos, com variações fisiológicas e interferências externas.|
| **Atuadores (A)** | Motores/servomotores controlados por sistema embarcado para aplicar torque compensatório com segurança. |
| **Sensores (S) ** | EMG, IMU, encoders e sensores de torque/corrente para detectar intenção, tremor e garantir controle em malha fechada. |

---

### 4. Arquitetura de Dados e IA
Definição das fontes de dados e da inteligência por trás da solução.

* **Origem dos Dados:** [Parkinson Disease Detection].
* **Lógica de IA:** [Controladores Inteligentes/Fuzzy].
* **Justificativa:** Essa técnica — combinando Redes Neurais e controle inteligente — é ideal para esse problema porque a Doença de Parkinson envolve sinais motores altamente não lineares, variáveis e cheios de ruído, o que dificulta o uso de métodos tradicionais com parâmetros fixos. As Redes Neurais conseguem aprender padrões complexos dos sinais (como diferenciar tremor de movimento voluntário), enquanto técnicas como Lógica Fuzzy ou controle adaptativo permitem gerar respostas suaves e graduais, mais próximas do comportamento humano. Além disso, essas abordagens se adaptam ao paciente ao longo do tempo, acompanhando a progressão da doença, o que torna o sistema mais robusto, personalizado e eficaz em situações reais.

---

### 5. Plano de Tratamento de Dados (ETL)
O fluxo de processamento dos dados segue estas etapas:
1. **Extração:** Coleta de dados via arquivos [Parkinsson disease.csv] ou simulação.
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

### 7. Instruções para Execução
Para reproduzir o ambiente e testar o diagnóstico:
1. Clone este repositório.
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
