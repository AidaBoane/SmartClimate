# Projeto: SmartClimate - Monitor de Conforto Térmico e Risco de Condensação

## Identificação
- **Universidade:** Universidade Europeia
- **Faculdade:** Faculdade de Design, Tecnologia e Comunicação
- **Curso:** Engenharia Informática On-line (5.º Semestre)
- **Estudante:** Aida Boane (20141956)
- **Unidades Curriculares:** Sistemas Distribuídos, Computação Física e IoT, Inteligência Artificial, Engenharia de Software
- **Repositório GitHub:** [Inserir Link do Repositório]

---

## 1. Descrição Completa do Objetivo do Projeto
Durante os meses de inverno, as habitações enfrentam frequentemente níveis elevados de humidade interior e variações térmicas bruscas. Este fenómeno propicia o aparecimento de condensação nas paredes e caixilharias, promovendo o desenvolvimento de fungos e prejudicando o conforto e a saúde dos residentes.

**Objetivos do Projeto:**
- Desenvolver um dispositivo inteligente baseado em ESP32 para monitorizar em tempo real a temperatura, a humidade relativa e a luminosidade de uma divisão.
- Persistir os dados recolhidos numa base de dados MySQL através de uma arquitetura de comunicação REST.
- Desenvolver um modelo de Inteligência Artificial capaz de cruzar os dados internos recolhidos com previsões meteorológicas externas para antecipar o risco de formação de condensação.
- Disponibilizar uma interface e alertas automatizados para mitigar problemas de microclima interior de forma preventiva.

## 2. Público-Alvo
Habitantes de residências, inquilinos e proprietários que pretendem monitorizar o microclima interior e prevenir problemas de humidade, condensação e desconforto térmico de forma automatizada e económica.

## 3. Levantamento de Hardware e Software Necessários
Para a implementação bem-sucedida da solução, foram selecionados os seguintes recursos:

- **Hardware:**
  - **Microcontrolador ESP32:** Unidade central com Wi-Fi e Bluetooth integrados para processamento e comunicação.
  - **Sensor DHT22:** Sensor de alta precisão para medição da temperatura e humidade relativa do ar.
  - **Sensor LDR (Light Dependent Resistor):** Para monitorização da luminosidade ambiente.
  - **Display OLED I2C (SSD1306):** Para exibição local de métricas e alertas em tempo real.
  - **Breadboard e Cabos Jumpers:** Para a montagem física do protótipo sem necessidade de soldadura.

- **Software:**
  - **Firmware:** VS Code com a extensão PlatformIO (desenvolvimento em C++).
  - **Backend e API:** Servidor REST para receção e tratamento de dados.
  - **Base de Dados:** MySQL para o armazenamento relacional e histórico dos dados ambientais.
  - **Inteligência Artificial:** Python para execução do modelo preditivo de ponto de orvalho e consumo de API meteorológica externa.
  - **Controlo de Versões:** Git e GitHub para gestão do código-fonte e documentação.


## 4. Desenho da Infraestrutura Computacional
A infraestrutura do sistema adota uma arquitetura distribuída em camadas, estruturada da seguinte forma:

1. **Camada de Dispositivo (Edge / IoT):**
   - O microcontrolador ESP32 lê os dados do sensor DHT22 e apresenta feedback imediato no display OLED.
2. **Camada de Comunicação e Rede:**
   - Através da rede Wi-Fi doméstica, o ESP32 envia periodicamente os dados ambientais utilizando pedidos HTTP (API REST).
3. **Camada de Servidor e Persistência (Backend):**
   - O servidor processa os pedidos recebidos e armazena os registos de forma estruturada numa base de dados **MySQL**.
4. **Camada de Inteligência Artificial e Processamento Externo:**
   - Um módulo em Python consome uma API meteorológica externa para obter dados climáticos exteriores e executa o cálculo preditivo do ponto de orvalho, gerando alertas preventivos.


*(Esquema textual da infraestrutura)*
`[Sensor DHT22 / ESP32]` --(Wi-Fi / REST API)--> `[Servidor Backend / MySQL]` <--- `[Modelo de IA / Python & API Externa]`


## 5. Esboço do Artefacto Físico e Diagrama de Circuitos
O protótipo físico será montado numa breadboard seguindo o seguinte planeamento de ligações:
- **Alimentação:** O ESP32 fornece 3.3V e GND para alimentar o sensor DHT22 e o display OLED.
- **Sensor DHT22:** Ligado ao pino digital GPIO 4 do ESP32 para transmissão de dados de temperatura e humidade.
- **Display OLED I2C:** Ligado aos pinos SDA (GPIO 21) e SCL (GPIO 22).
- **Sensor LDR:** Integrado num divisor de tensão ligado a uma porta analógica (ADC) do ESP32.


## 6. Lista Preliminar de Material Necessário
- 1x Placa de Desenvolvimento ESP32 (DevKit V1 / NodeMCU com USB-C)
- 1x Sensor de Temperatura e Humidade DHT22
- 1x Display OLED I2C 0.96" (SSD1306)
- 1x Sensor LDR + Resistência de 10kΩ
- 1x Breadboard (Placa de ensaio)
- Cabos Jumpers (Macho-Macho e Macho-Fêmea)
- 1x Cabo USB para programação e alimentação

## 7. Plano de Trabalho e Metodologia (Engenharia de Software)
O desenvolvimento do projeto decorrerá de forma individual, abrangendo todo o ciclo de vida do software e hardware através das seguintes etapas:

1. **Ideação e Investigação do Problema:**
   - Identificação da necessidade de monitorização de condensação em habitações e pesquisa sobre soluções técnicas viáveis.
2. **Seleção Tecnológica e Levantamento de Requisitos:**
   - Escolha do kit de hardware (ESP32, DHT22) e definição formal dos requisitos funcionais e não funcionais do sistema.
3. **Desenho da Arquitetura e Infraestrutura:**
   - Modelação da comunicação distribuída, desenho do esquema computacional e planeamento da base de dados relacional.
4. **Esboço e Simulação do Hardware:**
   - Planeamento físico da montagem dos componentes na  
   breadboard.
5. **Codificação e Desenvolvimento (Implementação):**
   - Programação do firmware no PlatformIO para leitura dos sensores e envio via REST.
   - Desenvolvimento do backend, ligação à base de dados MySQL e implementação do modelo preditivo em Python.
6. **Testes e Validação:**
   - Execução de testes unitários e de integração para validar a cadeia completa de recolha de dados, persistência e emissão de alertas.
7. **Implantação e Entrega Final:**
   - Montagem final do protótipo físico, compilação da documentação final, produção do vídeo demonstrativo e poster académico.