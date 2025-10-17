# 🏔️ Sistema de Mineração - Utopia

## 📋 Visão Geral

Sistema completo de mineração com 3 etapas: **Mineração** → **Lavagem** → **Forja**. Cada etapa tem timers específicos, requisitos e recompensas diferentes.

---

## ⛏️ ETAPA 1: MINERAÇÃO

### 📍 Localização
- **Zona:** Mina de mineração
- **Coordenadas:** 16 pontos espalhados pela área de mineração
- **Raio de ação:** 1.5 metros

### ⏱️ Timers
- **Tempo de mineração:** 10 segundos
- **Cooldown entre minerações:** 2 segundos
- **Total por ciclo:** 12 segundos

### 🛠️ Requisitos
- **Ferramenta:** Picareta (obrigatória)
- **Preço da picareta:** $250

### 🎁 Recompensas
- **Item:** Pedra
- **Quantidade:** 5x (sempre fixo)
- **Taxa de sucesso:** 100%

### 📊 Economia
- **Tempo por pedra:** 2.4 segundos
- **Pedras por minuto:** 25
- **Pedras por hora:** 1,500

---

## 🧽 ETAPA 2: LAVAGEM

### 📍 Localização
- **Zona:** Pontos de lavagem
- **Coordenadas:** 2 pontos específicos
- **Raio de ação:** 1.5 metros

### ⏱️ Timers
- **Tempo de lavagem:** 8 segundos
- **Cooldown entre lavagens:** 2 segundos
- **Total por ciclo:** 10 segundos

### 🛠️ Requisitos
- **Ferramenta:** Peneira (obrigatória)
- **Preço da peneira:** $150
- **Input:** 15x Pedra (consumidas)

### 🎁 Recompensas
- **Item:** Pedra Lavada
- **Quantidade:** 15x (sempre fixo)
- **Taxa de sucesso:** 100%

### 📊 Economia
- **Tempo por pedra lavada:** 0.67 segundos
- **Pedras lavadas por minuto:** 90
- **Pedras lavadas por hora:** 5,400
- **Eficiência:** 1:1 (15 pedras → 15 pedras lavadas)

---

## 🔥 ETAPA 3: FORJA

### 📍 Localização
- **Zona:** Forja principal
- **Coordenadas:** 1 ponto específico
- **Raio de ação:** 1.5 metros

### ⏱️ Timers
- **Tempo de processamento:** 12 segundos
- **Cooldown entre processamentos:** 2 segundos
- **Total por ciclo:** 14 segundos

### 🛠️ Requisitos
- **Input:** 10x Pedra Lavada (consumidas)
- **Combustível:** Carvão (consumido gradualmente)
- **Preço do carvão:** $50

### 🌡️ Sistema de Temperatura

#### Configurações Básicas
- **Temperatura inicial:** 500°C
- **Temperatura mínima:** 500°C
- **Temperatura máxima:** 1,400°C
- **Temperatura mínima para processar:** 600°C

#### Controle de Temperatura
- **Boost por carvão adicionado:** +50°C (imediato)
- **Aquecimento com carvão:** +15°C por segundo
- **Resfriamento sem carvão:** -5°C por segundo
- **Duração do carvão:** 10 segundos por unidade

#### Faixas de Temperatura
| Faixa | Temperatura | Cor | Status |
|-------|-------------|-----|--------|
| ❄️ Muito Frio | < 600°C | Azul | Não processa |
| 🟡 Morno | 600-849°C | Amarelo | Rendimento baixo |
| 🟢 Temperatura Boa | 850-1149°C | Verde | Rendimento ideal |
| 🟠 Quente Demais | 1150-1299°C | Laranja | Rendimento reduzido |
| 🔴 Muito Quente | ≥ 1300°C | Vermelho | Rendimento mínimo |

### 🎁 Recompensas por Temperatura

#### ❄️ Muito Frio (< 600°C)
- **Resultado:** Nenhum item
- **Taxa de sucesso:** 0%

#### 🟡 Morno (600-849°C)
- **Ferro:** 70% chance (1-2x)
- **Cobre:** 30% chance (1-2x)

#### 🟢 Temperatura Boa (850-1149°C) - **IDEAL**
- **Ferro:** 40% chance (1-2x)
- **Prata:** 25% chance (1-2x)
- **Ouro:** 15% chance (1-2x)
- **Rubi:** 10% chance (1x)
- **Esmeralda:** 10% chance (1x)

#### 🟠 Quente Demais (1150-1299°C)
- **Ferro:** 60% chance (1x)
- **Cobre:** 40% chance (1x)

#### 🔴 Muito Quente (≥ 1300°C)
- **Cobre:** 100% chance (1x)

### 📊 Economia da Forja

#### Consumo de Recursos
- **Pedras lavadas por processamento:** 10x
- **Carvão necessário:** ~2-3x (depende da temperatura)
- **Tempo por processamento:** 14 segundos

#### Rendimento por Hora (Temperatura Ideal - 850-1149°C)
- **Processamentos por hora:** ~257
- **Pedras lavadas consumidas:** 2,570
- **Carvão consumido:** ~514-771

#### Itens Esperados por Hora (Temperatura Ideal)
- **Ferro:** ~103-206x (40% chance)
- **Prata:** ~64-128x (25% chance)
- **Ouro:** ~39-78x (15% chance)
- **Rubi:** ~26x (10% chance)
- **Esmeralda:** ~26x (10% chance)

---

## 💰 Análise Econômica Completa

### Custo de Ferramentas
- **Picareta:** $250 (uso ilimitado)
- **Peneira:** $150 (uso ilimitado)
- **Carvão:** $50 por unidade

### Fluxo de Produção Completo

#### Para 1 Processamento na Forja:
1. **Mineração:** 2x ciclos (20 segundos) = 10 pedras
2. **Lavagem:** 1x ciclo (10 segundos) = 10 pedras lavadas
3. **Forja:** 1x ciclo (14 segundos) = 1 processamento

**Total:** 44 segundos para 1 processamento completo

#### Produção por Hora:
- **Processamentos completos:** ~82
- **Pedras mineradas:** 820
- **Pedras lavadas:** 820
- **Carvão consumido:** ~164-246

### Valor dos Itens (Exemplo)
*Nota: Os preços devem ser configurados no sistema de vendas*

| Item | Quantidade/Hora | Valor Estimado |
|------|----------------|----------------|
| Ferro | 33-66x | $X por unidade |
| Prata | 20-41x | $X por unidade |
| Ouro | 12-25x | $X por unidade |
| Rubi | 8x | $X por unidade |
| Esmeralda | 8x | $X por unidade |

---

## 🎯 Dicas de Otimização

### Para Máximo Rendimento:
1. **Mantenha a temperatura entre 850-1149°C**
2. **Adicione carvão gradualmente** para controlar a temperatura
3. **Processe em lotes** para economizar tempo
4. **Monitore o consumo de carvão** para evitar desperdício

### Estratégias de Temperatura:
- **Início:** Adicione 2-3 carvões para atingir 600°C
- **Manutenção:** Adicione 1 carvão a cada 10-15 segundos
- **Ideal:** Mantenha entre 900-1100°C para melhor rendimento
- **Evite:** Temperaturas acima de 1150°C (degradação)

---

## ⚙️ Configurações Técnicas

### Arquivos de Configuração:
- **`config.lua`:** Timers, recompensas, localizações
- **`forge.js`:** Sistema de temperatura, interface
- **`server.lua`:** Lógica de recompensas, anti-cheat

### Personalização:
- Todos os timers podem ser ajustados no `config.lua`
- As porcentagens de recompensa podem ser modificadas
- As temperaturas podem ser ajustadas no `forge.js`
- Os preços dos itens podem ser alterados

---

## 🔧 Suporte

Para dúvidas ou problemas:
1. Verifique os logs do console
2. Confirme se tem as ferramentas necessárias
3. Verifique se está na zona correta
4. Consulte este README para referência

---

*Sistema desenvolvido para Utopia - Versão 1.0*
