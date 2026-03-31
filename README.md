# 🚀 Ignition Zero — O Início da Aurora

> Relatório Operacional de Pré-Decolagem da Nave Aurora Siger  
> Missão simulada desenvolvida como atividade integradora da Fase 1 — FIAP

---

## 📋 Sobre o projeto

O **Ignition Zero** é uma simulação de sistema embarcado de verificação de pré-decolagem para a nave **Aurora Siger**, desenvolvida como atividade integradora do primeiro semestre da FIAP.

O projeto integra cinco disciplinas da Fase 1:

- **Computer Science** — lógica booleana, sistemas numéricos e representação de dados
- **Pensamento Computacional e Python** — algoritmos, fluxogramas e automação
- **Prompt & Artificial Intelligence** — triagem de dados assistida por IA
- **Soluções em Energias Renováveis** — análise de consumo e eficiência energética
- **Formação Social e Sustentabilidade** — ética, impacto social e responsabilidade tecnológica

O estudante assume o papel de **analista de missão**, responsável por validar os parâmetros técnicos da nave antes da decolagem — decidindo entre **"PRONTO PARA DECOLAR"** ou **"DECOLAGEM ABORTADA"**.

---

## 🗂️ Estrutura do projeto

```
ignition-zero/
│
├── ignition_zero.ipynb        # Notebook principal com o script de verificação
├── README.md                  # Este arquivo
└── relatorio/
    └── Ignition_Zero_Relatorio_Completo.pdf   # Relatório completo (etapas 1–6)
```

---

## ⚙️ O que o sistema faz

O notebook realiza a verificação automatizada de **17 parâmetros de telemetria** organizados em 5 categorias:

| Categoria | Parâmetros verificados |
|---|---|
| 🌡️ Temperatura | Cabine, Casco externo, Motores |
| 🏗️ Integridade estrutural | Status geral (0 = falha / 1 = OK) |
| ⚡ Energia | Bateria principal, Bateria backup, Energia solar |
| 🔧 Pressão dos tanques | Combustível, LOX, Hélio/N₂, Cabine |
| 🖥️ Módulos críticos | Navegação, Controle de voo, Comunicação, Suporte à vida, Motores, Abortagem |

Ao final da verificação, o sistema imprime o resultado:

```
🟢 RESULTADO: PRONTO PARA DECOLAR
   Todos os sistemas estão dentro das faixas seguras.
```

ou

```
🔴 RESULTADO: DECOLAGEM ABORTADA
   Corrija os itens com ❌ antes de prosseguir.
```

---

## 🖼️ Prints da execução

### Célula 1 — Carregamento dos dados de telemetria
```
✅ Dados de telemetria carregados com sucesso.
```

### Célula 2 — Verificação dos parâmetros
```
==================================================
 VERIFICAÇÃO DE TELEMETRIA — IGNITION ZERO
==================================================

🌡 TEMPERATURA
  ✅ Cabine: 22.5°C (faixa: 18–27°C)
  ✅ Casco externo: 15.0°C (faixa: -50 a +60°C)
  ✅ Motores: 35.0°C (faixa: 15–40°C)

🏗 INTEGRIDADE ESTRUTURAL
  ✅ Integridade: 1 (esperado: 1)

⚡ ENERGIA
  ✅ Bateria principal: 97.0% (mín: 85%)
  ✅ Bateria backup: 90.0% (mín: 85%)
  ✅ Energia solar: 92.0% (mín: 90%)

🔧 PRESSÃO DOS TANQUES
  ✅ Combustível: 325.0 kPa (300–350)
  ✅ LOX (oxidante): 300.0 kPa (280–320)
  ✅ Hélio/N₂: 4200.0 kPa (4.000–4.500)
  ✅ Cabine: 101.0 kPa (96–104)

🖥 MÓDULOS CRÍTICOS
  ✅ Navegação: ONLINE
  ✅ Controle de voo: ONLINE
  ✅ Comunicação: ONLINE
  ✅ Suporte à vida: ONLINE
  ✅ Motores: ONLINE
  ✅ Sistema de abortagem: ONLINE
```

### Célula 3 — Resultado final
```
==================================================
 Verificações: 17 aprovadas | 0 com falha
==================================================

 🟢 RESULTADO: PRONTO PARA DECOLAR
    Todos os sistemas estão dentro das faixas seguras.
==================================================
```

---

## ▶️ Como executar o código

### Pré-requisitos

- Python **3.8 ou superior**
- Jupyter Notebook ou Jupyter Lab instalado

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/ignition-zero.git
cd ignition-zero
```

2. (Opcional) Crie um ambiente virtual:
```bash
python -m venv venv
source venv/bin/activate        # Linux/Mac
venv\Scripts\activate           # Windows
```

3. Instale o Jupyter (se ainda não tiver):
```bash
pip install notebook
```

### Execução

1. Abra o Jupyter Notebook:
```bash
jupyter notebook
```

2. No navegador, abra o arquivo `ignition_zero.ipynb`

3. Execute as células **na ordem**:
   - **Célula 1** — define os dados de telemetria
   - **Célula 2** — executa o algoritmo de verificação
   - **Célula 3** — exibe o resultado final

4. Para simular uma falha, altere qualquer valor fora da faixa segura na Célula 1 e re-execute. Exemplo:
```python
"bateria_principal": 70.0,   # abaixo do mínimo de 85% → aborto
```

---

## 📊 Faixas seguras de referência

| Parâmetro | Mínimo | Máximo | Unidade |
|---|---|---|---|
| Temp. cabine | 18 | 27 | °C |
| Temp. casco | -50 | +60 | °C |
| Temp. motores | 15 | 40 | °C |
| Bateria principal | 85 | 100 | % |
| Bateria backup | 85 | 100 | % |
| Energia solar | 90 | 100 | % |
| Pressão combustível | 300 | 350 | kPa |
| Pressão LOX | 280 | 320 | kPa |
| Pressão Hélio/N₂ | 4000 | 4500 | kPa |
| Pressão cabine | 96 | 104 | kPa |

> Qualquer módulo crítico com status `0` (OFFLINE) resulta em **DECOLAGEM ABORTADA** automaticamente.

---

## 👨‍🚀 Autor

**Denis Urbano Cereto** — RM569187  
FIAP — Fase 1 · Ignition Zero: O Início da Aurora  

---

## 📚 Referências

- NASA. *Autonomous Systems*. Disponível em: https://www.nasa.gov/centers-and-facilities/armstrong/autonomous-systems/
- ESA. *European Space Agency*. Disponível em: https://www.esa.int/
- SpaceX. *Starship*. Disponível em: https://www.spacex.com/vehicles/starship
