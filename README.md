# 🍃 Leaf Sense (SIMV) - Challenge CCR Motiva

**Sistema Inteligente de Monitoramento de Vegetação Rodoviária (SIMV)** desenvolvido como solução tecnológica para o **Challenge CCR Motiva 2026** (FIAP)[cite: 32]. O projeto alcançou a fase final da competição, classificando-se entre os **12 melhores (Top 12)**[cite: 36].

## 🎯 O Problema
O controle de vegetação e canteiros em rodovias operava sob um modelo reativo e baseado em cronogramas fixos (ex: podas a cada 30 dias)[cite: 32, 35]. A ausência de dados em tempo real gerava dois extremos ineficientes para a concessionária[cite: 32]:
1. Custos operacionais (OPEX) inflacionados com frotas de poda em áreas sem necessidade[cite: 32, 35].
2. Intervenções tardias que comprometem a segurança viária, ocultando sinalizações[cite: 32, 35].

## 💡 A Solução e Arquitetura de Software
O Leaf Sense propõe a transição de um modelo de engenharia reativo para um ecossistema inteiramente preditivo[cite: 34, 36]. A arquitetura foi dividida em três camadas principais[cite: 33, 34]:

### 1. Ingestão de Dados (Borda)
Captura massiva de informações visuais através de câmeras de alta frequência acopladas aos veículos de patrulha de rotina da concessionária (10 fotos por segundo)[cite: 33]. A rodovia é indexada logicamente em trechos de 500 metros[cite: 33].

### 2. Visão Computacional (Processamento)
Pipeline em Python e OpenCV rodando no backend para[cite: 36]:
* Aplicação de Filtros Espaciais (ROI - *Region of Interest*) para focar exclusivamente na margem e solo da via, eliminando falsos positivos com copas de árvores[cite: 36].
* Segmentação de imagens e cálculo dimensional, estimando a altura do mato em centímetros através de *bounding boxes* e fatores de conversão[cite: 34, 36].

### 3. Inteligência Preditiva Autônoma
Modelo orquestrado via n8n e API da OpenAI[cite: 36]. A IA correlaciona o tamanho atual da vegetação, dados de pluviosidade/temperatura local e o histórico de manutenções para emitir alertas preditivos de poda, evitando que o limite regulamentar seja ultrapassado[cite: 34, 35, 36].

## 🖥️ Dashboard Operacional (Frontend)
A interface de operação foi desenvolvida em HTML, CSS e JavaScript puros[cite: 31, 36], entregando[cite: 36]:
* **Mapeamento Interativo:** Renderização visual dos trechos georreferenciados[cite: 36].
* **Painéis Operacionais:** Exibição de alertas preventivos, status de cobertura da malha e índices climáticos[cite: 36].

## 🛠️ Stack Tecnológico
* **Computer Vision:** Python, OpenCV, NumPy, Matplotlib, Google Colab[cite: 36, 39].
* **IA & Automação:** n8n, OpenAI API (LLMs para simulação e lógica preditiva)[cite: 36].
* **Frontend:** HTML5, CSS3, JavaScript (`map.js`, `dashboard.js`, `prediction.js`, `weather.js`).

## 🚀 Como Executar
1. Faça o clone do repositório:
   ```bash
   git clone [https://github.com/TaysirAli/leaf-sense-simv.git](https://github.com/TaysirAli/leaf-sense-simv.git)
