# Neurofeedback Homem-Robô – Alinhamento Cognitivo-Fisiológico

Monitoramento em tempo real (ou quasi-real) de **POG**, **EEG**, **ECG** e **ADA**  
para avaliar e promover **alinhamento** entre operador humano e sistema robótico/autônomo.

Projeto hospedado no **Google Apps Script** (script.google.com)  
→ atua como **middleware leve**, dashboard simples e/ou receptor de dados.

## 🔴 O que cada sinal representa neste contexto

| Sinal | Nome completo                  | O que tentamos capturar no alinhamento H-R                  | Interpretação comum no neurofeedback HRI                     |
|------|--------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|
| POG  | Point of Gaze / Pupilato       | Para onde o humano está olhando (atenção visual)             | Sincronia visual com o robô / joint attention                 |
| EEG  | Eletroencefalograma            | Estados cognitivos / emocionais / carga mental / foco         | Alpha/theta/beta/gamma, workload, engajamento, frustração     |
| ECG  | Eletrocardiograma              | Ativação autonômica / estresse / excitação emocional          | HR, HRV (RMSSD, SDNN), coerência cardíaca                     |
| ADA  | Ativação do Sistema Nervoso Autônomo (estimada) | Balanceamento simpático-parassimpático (via HRV + outros)   | Co-regulação emocional, rapport fisiológico com a máquina     |

Objetivo principal  
→ Detectar e quantificar **momentos de alinhamento/desalinhamento** entre humano e robô  
→ Fornecer **feedback em loop fechado** (visual, sonoro, vibrotátil ou comando no robô)

## Funcionalidades atuais (mar/2026)

- Recebimento de dados via HTTP POST (de dispositivo wearable / BCI / eye-tracker)
- Armazenamento em Google Sheets (timestamp + 4 sinais + metadados)
- Cálculo simples de indicadores de alinhamento (exemplos):
  - Coerência HRV
  - % de tempo olhando para o robô (POG)
  - Índice de carga mental (beta/alpha ratio ou proxy)
  - Score composto de "alinhamento fisiológico" (0–100)
- Dashboard básico em HTML (Google Apps Script Web App)
  - Gráficos lineares atualizados a cada 5–30 segundos
  - Indicadores de status (verde / amarelo / vermelho)
  - Últimos 3–5 minutos de dados
- Alertas via e-mail / Telegram quando desalinhamento crítico é detectado

## Roadmap pretendido (próximos passos)

- [ ] Integração direta com Telegram / WhatsApp para feedback em tempo real
- [ ] Cálculo de coerência entre sinais (ex: Phase Locking Value entre EEG e HRV)
- [ ] Feedback adaptativo no robô (velocidade, tom de voz, expressão facial)
- [ ] Exportação automática para análise offline (CSV / JSON)
- [ ] Validação mínima com pelo menos 3 usuários (estudo piloto)
- [ ] Tentativa de modelo simples de machine learning no Apps Script (regressão logística leve)

## Como os dados chegam ao script (fluxo típico)
