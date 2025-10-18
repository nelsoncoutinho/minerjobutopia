# 🪨 UT_MINER - Sistema de Mineração

## 📋 Índice
- [Visão Geral](#visão-geral)
- [Fluxo do Trabalho](#fluxo-do-trabalho)
- [Sistema de Temperaturas](#sistema-de-temperaturas)
- [Tabela de Probabilidades](#tabela-de-probabilidades)
- [Cálculos de Rentabilidade](#cálculos-de-rentabilidade)
- [Preços Recomendados](#preços-recomendados)
- [Tempos de Processamento](#tempos-de-processamento)

---

## 🎯 Visão Geral

O sistema de mineração possui **3 etapas** principais:
1. **Mineração** - Obter pedras brutas
2. **Lavagem** - Transformar pedras brutas em pedras lavadas
3. **Processamento (Forja)** - Fundir pedras lavadas em minérios valiosos

---

## 🔄 Fluxo do Trabalho

### **ETAPA 1: Mineração** ⛏️
- **Local:** Pontos de mineração (16 locais disponíveis)
- **Requisito:** Picareta (opcional, configurável)
- **Tempo:** 10 segundos por mineração
- **Cooldown:** 2 segundos entre minerações
- **Resultado:** **5 pedras** (quantidade fixa)

### **ETAPA 2: Lavagem** 💧
- **Local:** Pontos de lavagem (2 locais disponíveis)
- **Requisito:** Peneira + 15 pedras brutas
- **Tempo:** 8 segundos
- **Cooldown:** 2 segundos
- **Resultado:** **15 pedras lavadas** (quantidade fixa, conversão 1:1)

### **ETAPA 3: Processamento na Forja** 🔥
- **Local:** Forja Principal (1 local)
- **Requisitos:** 
  - 10 pedras lavadas (consumidas)
  - 2 carvões (consumidos)
- **Tempo:** 12 segundos
- **Resultado:** 1-2 minérios (dependendo do item e temperatura)

---

## 🌡️ Sistema de Temperaturas

A temperatura da forja é **CRUCIAL** e afeta diretamente:
- **Probabilidade** de obter itens raros
- **Quantidade** de itens obtidos
- **Qualidade** dos materiais

### Faixas de Temperatura

| Temperatura | Status | Efeito | Ícone |
|------------|--------|--------|-------|
| **< 600°C** | ❄️ Muito Frio | **FALHA TOTAL** - Não produz nada | ❄️ |
| **600-850°C** | 🟡 Morno | Pouco rendimento, materiais comuns | 🟡 |
| **850-1150°C** | 🟢 **IDEAL** | **Melhor rendimento**, materiais valiosos | 🟢 |
| **1150-1300°C** | 🟠 Quente Demais | Materiais degradam, perde qualidade | 🟠 |
| **> 1300°C** | 🔴 Crítico | Forja queima materiais, mínimo rendimento | 🔴 |

### Mecânica de Temperatura

#### 🔥 Aquecimento
- **1 Carvão** adicionado: +15°C instantâneo
- **Com carvão ativo:** +20°C por segundo
- **Temperatura máxima:** 1400°C

#### ❄️ Resfriamento
- **Sem carvão:** -5°C por segundo (resfriamento natural)
- **Temperatura mínima:** 500°C

#### ⏱️ Duração do Carvão
- **1 Carvão dura aproximadamente 20 segundos**
- Consumo gradual enquanto aquece a forja

---

## 📊 Tabela de Probabilidades

### ❄️ Temperatura < 600°C (Muito Frio)
```
❌ NÃO PRODUZ NADA
Mensagem: "Frio demais, nada se funde assim."
```

### 🟡 Temperatura 600-850°C (Morno)
| Item | Probabilidade | Quantidade | Valor Atual |
|------|--------------|------------|-------------|
| Ferro | 70% | 1-2x | $80 |
| Cobre | 30% | 1-2x | $120 |

**Rendimento médio:** Baixo - Apenas materiais comuns

### 🟢 Temperatura 850-1150°C (IDEAL) ⭐
| Item | Probabilidade | Quantidade | Valor Atual |
|------|--------------|------------|-------------|
| Ferro | 35% | 1-2x | $80 |
| Cobre | 20% | 1-2x | $120 |
| Prata | 18% | 1-2x | $200 |
| Ouro | 12% | 1-2x | $350 |
| Rubi | 5% | **1x** (fixo) | $600 |
| Esmeralda | 5% | **1x** (fixo) | $650 |
| Diamante | 5% | **1x** (fixo) | $800 |

**Rendimento médio:** Alto - Melhor zona para lucro

### 🟠 Temperatura 1150-1300°C (Quente Demais)
| Item | Probabilidade | Quantidade | Valor Atual |
|------|--------------|------------|-------------|
| Ferro | 60% | **1x** (fixo) | $80 |
| Cobre | 40% | **1x** (fixo) | $120 |

**Rendimento médio:** Baixo - Materiais degradados

### 🔴 Temperatura > 1300°C (Muito Quente)
| Item | Probabilidade | Quantidade | Valor Atual |
|------|--------------|------------|-------------|
| Cobre | 100% | **1x** (fixo) | $120 |

**Rendimento médio:** Mínimo - Tudo queimado

---

## 💰 Cálculos de Rentabilidade

### Custos Fixos (Loja de Equipamentos)
```
Picareta: $250 (compra única, não quebra)
Peneira: $150 (compra única, não quebra)
Carvão: $50 por unidade
```

### Ciclo Completo (Temperatura IDEAL 850-1150°C)

#### 📊 Processo para obter 10 pedras lavadas:
1. **Mineração:** 2 minerações (5 pedras cada) = 10 pedras brutas
2. **Lavagem:** Não aplicável neste ciclo (precisa 15 pedras)

#### 📊 Processo completo (45 pedras brutas → 30 pedras lavadas → 3 processamentos):

```
MINERAÇÃO (45 pedras brutas):
- Quantidade de minerações: 9x (45 ÷ 5)
- Tempo total: 9 × 10s = 90 segundos (1min 30s)
- Cooldown: 9 × 2s = 18 segundos
- Total: 108 segundos (1min 48s)

LAVAGEM (45 pedras → 45 pedras lavadas):
- Quantidade de lavagens: 3x (45 ÷ 15)
- Tempo total: 3 × 8s = 24 segundos
- Cooldown: 3 × 2s = 6 segundos
- Total: 30 segundos

PROCESSAMENTO (45 pedras lavadas → minérios):
- Quantidade de processamentos: 4x (40 pedras ÷ 10)
- Tempo total: 4 × 12s = 48 segundos
- Carvão necessário: 4 × 2 = 8 carvões
- Total: 48 segundos

CUSTO:
- 8 carvões × $50 = $400

TEMPO TOTAL: 108s + 30s + 48s = 186 segundos (3min 6s)
```

### 📈 Lucro Esperado por Temperatura (4 processamentos)

#### 🟢 TEMPERATURA IDEAL (850-1150°C)
```
Probabilidades esperadas em 4 processamentos:

Ferro (35%): ~1.4 vezes → 1.4 × 1.5 (média) = 2.1 unidades → $168
Cobre (20%): ~0.8 vez → 0.8 × 1.5 (média) = 1.2 unidades → $144
Prata (18%): ~0.72 vez → 0.72 × 1.5 (média) = 1.08 unidades → $216
Ouro (12%): ~0.48 vez → 0.48 × 1.5 (média) = 0.72 unidades → $252
Rubi (5%): ~0.2 vez → 0.2 × 1 (fixo) = 0.2 unidades → $120
Esmeralda (5%): ~0.2 vez → 0.2 × 1 (fixo) = 0.2 unidades → $130
Diamante (5%): ~0.2 vez → 0.2 × 1 (fixo) = 0.2 unidades → $160

RECEITA MÉDIA: $1,190
CUSTO: $400 (carvão)
LUCRO MÉDIO: $790
LUCRO POR HORA: ~$15,130 (3min 6s por ciclo)
```

#### 🟡 TEMPERATURA MORNA (600-850°C)
```
Probabilidades esperadas em 4 processamentos:

Ferro (70%): ~2.8 vezes → 2.8 × 1.5 (média) = 4.2 unidades → $336
Cobre (30%): ~1.2 vezes → 1.2 × 1.5 (média) = 1.8 unidades → $216

RECEITA MÉDIA: $552
CUSTO: $400 (carvão)
LUCRO MÉDIO: $152
LUCRO POR HORA: ~$2,909 (3min 6s por ciclo)
```

#### 🟠 TEMPERATURA QUENTE DEMAIS (1150-1300°C)
```
Probabilidades esperadas em 4 processamentos:

Ferro (60%): ~2.4 vezes → 2.4 × 1 (fixo) = 2.4 unidades → $192
Cobre (40%): ~1.6 vezes → 1.6 × 1 (fixo) = 1.6 unidades → $192

RECEITA MÉDIA: $384
CUSTO: $400 (carvão)
LUCRO MÉDIO: -$16 (PREJUÍZO)
LUCRO POR HORA: ~-$307 (PREJUÍZO)
```

#### 🔴 TEMPERATURA MUITO QUENTE (> 1300°C)
```
Probabilidades esperadas em 4 processamentos:

Cobre (100%): 4 vezes → 4 × 1 (fixo) = 4 unidades → $480

RECEITA MÉDIA: $480
CUSTO: $400 (carvão)
LUCRO MÉDIO: $80
LUCRO POR HORA: ~$1,532 (3min 6s por ciclo)
```

---

## 💎 Preços Recomendados

### Preços Atuais vs Recomendados

Com base na análise de rentabilidade e raridade:

| Item | Preço Atual | Raridade | Preço Recomendado | Justificativa |
|------|-------------|----------|-------------------|---------------|
| **Ferro** | $80 | Comum (35%) | $80-100 | Material básico, alta probabilidade |
| **Cobre** | $120 | Comum (20%) | $100-130 | Material comum, boa disponibilidade |
| **Prata** | $200 | Raro (18%) | $200-250 | Material intermediário, boa taxa |
| **Ouro** | $350 | Raro (12%) | $350-400 | Material valioso, taxa média |
| **Rubi** | $600 | Muito Raro (5%) | $600-700 | Gema rara, quantidade fixa (1x) |
| **Esmeralda** | $650 | Muito Raro (5%) | $650-750 | Gema rara, quantidade fixa (1x) |
| **Diamante** | $800 | Muito Raro (5%) | $800-1000 | Gema raríssima, quantidade fixa (1x) |

### 🎯 Análise de Balanceamento

#### ✅ Bem Balanceado
- **Temperatura IDEAL (850-1150°C):** Lucro médio de ~$790 por ciclo (~$15,130/hora)
- **Incentivo para jogar corretamente:** Diferença significativa entre temperatura ideal e outras
- **Risco vs Recompensa:** Requer gestão ativa da temperatura
- **Sistema de Gemas Raras:** 3 gemas raras (5% cada) adicionam variedade e emoção

#### ⚠️ Pontos de Atenção
1. **Temperatura Quente (1150-1300°C):** PREJUÍZO! Incentiva jogadores a controlarem melhor
2. **Temperatura Morna (600-850°C):** Lucro baixo ($152) - incentiva buscar temperatura ideal
3. **Muito Quente (>1300°C):** Lucro mínimo ($80) - punição por descuido

### 💡 Sugestões de Ajuste

Se quiser **aumentar a dificuldade/tempo de farm:**
```
Ferro: $70 (-12%)
Cobre: $100 (-17%)
Prata: $180 (-10%)
Ouro: $320 (-9%)
Rubi: $550 (-8%)
Esmeralda: $600 (-8%)
Diamante: $700 (-12%)

Novo lucro médio (temp ideal): ~$680/ciclo (~$13,010/hora)
```

Se quiser **diminuir a dificuldade/tempo de farm:**
```
Ferro: $100 (+25%)
Cobre: $140 (+17%)
Prata: $250 (+25%)
Ouro: $400 (+14%)
Rubi: $700 (+17%)
Esmeralda: $750 (+15%)
Diamante: $1000 (+25%)

Novo lucro médio (temp ideal): ~$950/ciclo (~$18,190/hora)
```

---

## ⏱️ Tempos de Processamento

### Resumo de Tempos

| Ação | Tempo | Cooldown |
|------|-------|----------|
| Mineração | 10s | 2s |
| Lavagem | 8s | 2s |
| Processamento | 12s | 2s |

### Ciclo Completo (4 processamentos)

```
┌─────────────────────────────────────┐
│  ETAPA 1: MINERAÇÃO                 │
│  9 minerações × (10s + 2s) = 108s   │
│  Resultado: 45 pedras brutas        │
└─────────────────────────────────────┘
           ↓
┌─────────────────────────────────────┐
│  ETAPA 2: LAVAGEM                   │
│  3 lavagens × (8s + 2s) = 30s       │
│  Resultado: 45 pedras lavadas       │
└─────────────────────────────────────┘
           ↓
┌─────────────────────────────────────┐
│  ETAPA 3: PROCESSAMENTO             │
│  4 processamentos × 12s = 48s       │
│  Custo: 8 carvões ($400)            │
│  Resultado: 4-8 minérios            │
└─────────────────────────────────────┘

TEMPO TOTAL: 186 segundos (3min 6s)
```

---

## 📌 Notas Importantes

### Gerenciamento de Temperatura
- **SEMPRE mantenha a temperatura entre 850-1150°C** para melhor lucro
- Use carvão estrategicamente: 1 carvão = +20°/s por ~20 segundos
- Evite ultrapassar 1150°C - materiais degradam
- Temperatura < 600°C = desperdício total

### Estratégias de Lucro

#### 🏆 Estratégia Ótima
1. Comprar **20-30 carvões** de uma vez
2. Minerar até ter **45-60 pedras brutas**
3. Lavar todas as pedras de uma vez
4. Processar mantendo **temperatura ideal (850-1150°C)**
5. **Lucro esperado:** ~$900-1000 por ciclo

#### 💡 Estratégia Conservadora
1. Comprar **10 carvões**
2. Minerar até ter **30 pedras brutas**
3. Processar com cuidado
4. **Lucro esperado:** ~$450-500 por ciclo

---

## 🔧 Configurações Técnicas

### Arquivos Importantes
- `config.lua` - Configurações gerais, probabilidades, preços
- `server/server.lua` - Lógica de processamento e anti-cheat
- `html/forge.js` - Sistema de temperatura e interface

### Anti-Cheat
- Verificação de distância (máx: 10 metros)
- Rate limiting (10 ações/minuto)
- Validação server-side de todos os itens
- Logs completos no Discord webhook

---

## 📞 Suporte

Para ajustes nos preços, edite `config.lua`:

```lua
Config.BuyerItems = {
    { name = 'ferro', price = 80 },
    { name = 'cobre', price = 120 },
    { name = 'prata', price = 200 },
    { name = 'ouro', price = 350 },
    { name = 'ruby', price = 600 },
    { name = 'esmeralda', price = 650 },
    { name = 'diamante', price = 800 }
}
```

---

**Desenvolvido por:** Utopia RP  
**Versão:** 1.0.0  
**Última atualização:** Outubro 2025
