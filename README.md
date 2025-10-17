# 🏔️ Sistema de Mineração - Utopia

## 📋 Visão Geral

Sistema completo de mineração com 3 etapas: **Mineração** → **Lavagem** → **Forja**. Cada etapa tem temporizadores específicos, requisitos e recompensas diferentes.

---

## ⛏️ ETAPA 1: MINERAÇÃO

### 📍 Localização
- **Zona:** Mina de mineração
- **Coordenadas:** 16 pontos espalhados pela área de mineração
- **Raio de ação:** 1.5 metros

### ⏱️ Temporizadores
- **Tempo de mineração:** 10 segundos
- **Tempo de espera entre minerações:** 2 segundos
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

### ⏱️ Temporizadores
- **Tempo de lavagem:** 8 segundos
- **Tempo de espera entre lavagens:** 2 segundos
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

### ⏱️ Temporizadores
- **Tempo de processamento:** 12 segundos
- **Tempo de exibição do item:** 4 segundos
- **Tempo de espera entre processamentos:** 2 segundos
- **Total por ciclo:** 18 segundos (12s processamento + 4s exibição + 2s espera)

### 🛠️ Requisitos
- **Input:** 10x Pedra Lavada por processamento (consumidas em lote)
- **Combustível:** 2x Carvão por processamento (consumido por lote)
- **Preço do carvão:** $50

### 🌡️ Sistema de Temperatura

#### Configurações Básicas
- **Temperatura inicial:** 500°C
- **Temperatura mínima:** 500°C
- **Temperatura máxima:** 1,400°C
- **Temperatura mínima para processar:** 600°C

#### Controlo de Temperatura
- **Impulso por carvão adicionado:** +15°C (imediato, mais gradual)
- **Aquecimento com carvão:** +20°C por segundo (mais gradual)
- **Arrefecimento sem carvão:** -5°C por segundo (mais gradual)
- **Duração do carvão:** 20 segundos por unidade (mais duradouro)
- **Controlo livre:** Podes adicionar carvão a qualquer momento, mesmo durante processamento

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
- **Ferro:** 70% probabilidade (1-2x)
- **Cobre:** 30% probabilidade (1-2x)

#### 🟢 Temperatura Boa (850-1149°C) - **IDEAL**
- **Ferro:** 40% probabilidade (1-2x)
- **Cobre:** 20% probabilidade (1-2x)
- **Prata:** 20% probabilidade (1-2x)
- **Ouro:** 10% probabilidade (1-2x)
- **Rubi:** 5% probabilidade (1x)
- **Esmeralda:** 5% probabilidade (1x)

#### 🟠 Quente Demais (1150-1299°C)
- **Ferro:** 60% probabilidade (1x)
- **Cobre:** 40% probabilidade (1x)

#### 🔴 Muito Quente (≥ 1300°C)
- **Cobre:** 100% probabilidade (1x)

### 📊 Economia da Forja

#### Consumo de Recursos
- **Pedras lavadas por processamento:** 10x (sempre em lote)
- **Carvão necessário:** 2x (sempre fixo por processamento)
- **Tempo por processamento:** 18 segundos (12s processamento + 4s exibição + 2s cooldown)

#### Rendimento por Hora (Temperatura Ideal - 850-1149°C)
- **Processamentos por hora:** ~200
- **Pedras lavadas consumidas:** 2,000
- **Carvão consumido:** 400 (2x por processamento)

#### Itens Esperados por Hora (Temperatura Ideal)
- **Ferro:** ~80-160x (40% probabilidade)
- **Cobre:** ~40-80x (20% probabilidade)
- **Prata:** ~40-80x (20% probabilidade)
- **Ouro:** ~20-40x (10% probabilidade)
- **Rubi:** ~10x (5% probabilidade)
- **Esmeralda:** ~10x (5% probabilidade)

---

## 💰 Análise Económica Completa

### Custo de Ferramentas
- **Picareta:** $250 (uso ilimitado)
- **Peneira:** $150 (uso ilimitado)
- **Carvão:** $50 por unidade

### Fluxo de Produção Completo

#### Para 1 Processamento na Forja:
1. **Mineração:** 2x ciclos (20 segundos) = 10 pedras
2. **Lavagem:** 1x ciclo (10 segundos) = 10 pedras lavadas
3. **Forja:** 1x ciclo (18 segundos) = 1 processamento (10 pedras)

**Total:** 48 segundos para 1 processamento completo

#### Produção por Hora:
- **Processamentos completos:** ~75
- **Pedras mineradas:** 750
- **Pedras lavadas:** 750
- **Carvão consumido:** 150 (2x por processamento)

### Valor dos Itens (Exemplo)
*Nota: Os preços devem ser configurados no sistema de vendas*

| Item | Quantidade/Hora | Valor Estimado |
|------|----------------|----------------|
| Ferro | 80-160x | $X por unidade |
| Cobre | 40-80x | $X por unidade |
| Prata | 40-80x | $X por unidade |
| Ouro | 20-40x | $X por unidade |
| Rubi | 10x | $X por unidade |
| Esmeralda | 10x | $X por unidade |

---

## 🎯 Dicas de Otimização

### Para Máximo Rendimento:
1. **Mantenha a temperatura entre 850-1149°C**
2. **Adicione carvão gradualmente** para controlar a temperatura
3. **Processe em lotes** para poupar tempo
4. **Monitore o consumo de carvão** para evitar desperdício
5. **Use o controlo livre de carvão** - adicione quando precisar de mais calor

### Estratégias de Temperatura:
- **Início:** Adicione 2-3 carvões para atingir 600°C
- **Manutenção:** Adicione 1 carvão a cada 20-30 segundos (carvão dura mais)
- **Ideal:** Mantenha entre 900-1100°C para melhor rendimento
- **Controlo:** Podes adicionar carvão a qualquer momento para controlar a temperatura
- **Evite:** Temperaturas acima de 1150°C (degradação)

---

## 🆕 Novas Funcionalidades

### 🔥 Sistema de Temperatura Melhorado
- **Controlo livre de carvão:** Podes adicionar carvão a qualquer momento, mesmo durante processamento
- **Temperatura mais gradual:** Aquecimento e arrefecimento mais suaves para melhor controlo
- **Carvão mais duradouro:** 1 carvão dura 20 segundos (em vez de 10)
- **Impulso mais suave:** +15°C por carvão (em vez de +50°C)

### 🎯 Processamento Optimizado
- **Processamento em lote:** 10x pedras lavadas por ciclo
- **Exibição do item:** Item aparece na forja por 4 segundos antes de ir para o inventário
- **Remoção automática:** Itens são removidos automaticamente do inventário quando adicionados à forja
- **Interface sem restrições:** Podes abrir a forja mesmo sem carvão no inventário

### 🖼️ Sistema de Imagens
- **Imagens do GitHub:** Todos os itens usam imagens directamente do repositório GitHub
- **Fallback automático:** Se a imagem não carregar, mostra a primeira letra do item

---

## ⚙️ Configurações Técnicas

### Ficheiros de Configuração:
- **`config.lua`:** Temporizadores, recompensas, localizações
- **`forge.js`:** Sistema de temperatura, interface
- **`server.lua`:** Lógica de recompensas, anti-cheat

### Personalização:
- Todos os temporizadores podem ser ajustados no `config.lua`
- As percentagens de recompensa podem ser modificadas
- As temperaturas podem ser ajustadas no `forge.js`
- Os preços dos itens podem ser alterados

---

## 🔧 Suporte

Para dúvidas ou problemas:
1. Verifique os logs da consola
2. Confirme se tem as ferramentas necessárias
3. Verifique se está na zona correcta
4. Consulte este README para referência

---

*Sistema desenvolvido para Utopia - Versão 1.0*
