# 📊 Análise e Insights sobre Gastos Médicos


### 📌 Análise de cada variável

- **Região**: Não apresenta relevância significativa para explicar as despesas médicas.
- **Número de filhos**: Embora possa contribuir para uma dispersão aleatória de casos com gastos mais altos, não há uma relação diretamente proporcional entre o número de filhos e as despesas médicas.
- **Sexo**: Não possui impacto significativo na previsão dos gastos médicos.
- **Índice de Massa Corporal (IMC)**: Um IMC alto está associado ao surgimento de outliers em regiões de gastos elevados, especialmente quando combinado com idade avançada e tabagismo.
- **Idade**: Para pessoas sem filhos, não fumantes e com IMC saudável, a idade demonstra uma correlação quase linear com os gastos médicos. No entanto, há outliers que podem ser explicados por outras condições médicas não presentes no dataset, como doenças crônicas.
- **Tabagismo**: O tabagismo é o principal fator de influência nos altos gastos médicos, sendo responsável por despesas que se concentram no quartil superior (Q4), gerando muitos outliers no conjunto de dados.

---

## 🤖 Considerações sobre o Modelo

O modelo baseado em **RandomForest** treinado apresenta os seguintes erros:

- **MAE (Erro Absoluto Médio - Validação)**: `1549.69` ± `53.11`
- **MAPE (Erro Percentual Absoluto Médio - Validação)**: `0.1525` ± `0.0132`

📌 **Interpretação dos erros:**
- A média de gastos médicos no dataset é de **12.784 dólares**, e **50% das despesas são menores que 9.443 dólares**.
- Um erro médio de **1549 dólares** pode ser significativo em situações que envolve gastos baixos.
- O modelo tem dificuldades em prever gastos elevados devido à menor quantidade de instâncias representando outliers no conjunto de dados.
- O modelo é **mais confiável para despesas mais baixas** e pode apresentar maior erro para valores altos.

⚠️ **Sugestão para previsões mais seguras:**
Ao prever um gasto alto, o valor estimado deve ser acompanhado por um intervalo de confiança baseado no MAE. Por exemplo:

> **Se o modelo prever 20.000 dólares, um intervalo seguro seria de 21.549 dólares, considerando o MAE como margem de erro.**

📌 **Melhoria do modelo:**
- Incluir mais instâncias representando **outliers** para um melhor aprendizado do modelo.
- Adicionar novas features, como **histórico de doenças crônicas**, para melhor generalização e compreensão dos padrões de gastos elevados.

---

## 🚀 Plano de Ação Proposto

Com base na análise exploratória e nas interações entre as variáveis, foram identificadas abordagens estratégicas para mitigar o problema de altos gastos médicos:

### 🩺 1. Acompanhamento médico preventivo para idosos
✅ **Objetivo**: Reduzir custos com tratamentos complexos e melhorar a previsibilidade financeira do plano de saúde.
- **Impacto esperado:**
  - Diagnósticos precoces evitam internações prolongadas e tratamentos caros.
  - Fidelização de clientes idosos ao oferecer um plano de saúde mais atrativo.
  - Melhoria no planejamento financeiro da empresa.

### 🚭 2. Medidas contra o tabagismo
✅ **Objetivo**: Reduzir a incidência de doenças associadas ao tabagismo e os custos médicos relacionados.
- **Ações propostas:**
  - Programas de suporte clínico e psicológico para quem deseja parar de fumar.
  - Cobertura de despesas com tratamento para cessação do tabagismo.
- **Impacto esperado:**
  - Redução de casos de doenças pulmonares, cardíacas e câncer.
  - Plano de saúde mais atrativo para empresas e segurados.
  - Melhoria na imagem institucional da operadora do plano.

### 🏋️‍♂️ 3. Acompanhamento nutricional e incentivo à atividade física
✅ **Objetivo**: Reduzir doenças relacionadas à obesidade e incentivar hábitos saudáveis.
- **Ações propostas:**
  - Consultas gratuitas para planejamento nutricional.
  - Parcerias com academias e oferta de programas como **GymPass**.
- **Impacto esperado:**
  - Menos casos de diabetes, hipertensão e problemas cardiovasculares.
  - Maior adesão de clientes jovens e ativos.
  - Redução da sinistralidade do plano de saúde.

---

## 📌 Conclusão Final

Os insights extraídos da análise dos dados mostram que **o tabagismo e o IMC elevado são os principais fatores associados a altos gastos médicos**, e que medidas preventivas podem ser adotadas para mitigar esses custos.

🔹 **O modelo preditivo funciona melhor para valores mais baixos de gastos médicos e pode apresentar erros maiores para previsões de despesas elevadas.**

🔹 **Recomenda-se o aprimoramento do modelo com mais dados representando outliers e a adição de novas variáveis, como doenças crônicas, para maior precisão.**

🔹 **O plano de ação sugerido pode trazer benefícios tanto para os usuários dos planos de saúde quanto para as operadoras, reduzindo custos e melhorando a qualidade dos serviços prestados.**

📌 **Próximos passos:**
- Investigar novas features que possam melhorar a precisão do modelo.
- Testar modelos mais robustos, como **Redes Neurais** para capturar padrões mais complexos.

