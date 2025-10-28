
# 🧪 FakeStore API — Teste de Carga e Relatório de Desempenho

Este projeto tem como objetivo **avaliar o desempenho do endpoint da API FakeStore** por meio de testes de carga automatizados, medindo tempos de resposta, throughput e estabilidade sob alta demanda.  
O relatório final apresenta **gargalos, métricas de desempenho e oportunidades de melhoria** para evolução da arquitetura da aplicação.

---

## 📌 Nome do Projeto

**FakeStore API — Load Test & Performance Report**

---

## 📄 Descrição Resumida

- API pública utilizada: `https://fakestoreapi.com/products/1`  
- Teste de carga com volume de requisições simultâneas para simular usuários reais.  
- Coleta e análise de métricas como:
  - Latência média e máxima  
  - Throughput (requisições por segundo)  
  - Desvio padrão de resposta  
  - Taxa de transferência de dados

---

## 🏗️ Arquitetura / Estrutura de Pastas

```plaintext
.
├── reports/
│   ├── Relatorio_FakeStore_API.md         # Relatório técnico com análise detalhada
│   ├── Relatorio_FakeStore_API.pdf        # Relatório em PDF com gráficos
│   ├── latencia_fakestore.png             # Gráfico de latência
│   └── throughput_fakestore.png           # Gráfico de throughput
├── tests/
│   ├── load_test.jmx                      # Script de teste JMeter
│   └── summary.csv                        # Arquivo gerado com os resultados do teste
├── scripts/
│   └── gerar_relatorio.py                # Script Python para gerar relatório automático
├── README.md                             # Este arquivo
└── requirements.txt                      # Dependências do projeto
```

---

## 🧰 Versões Utilizadas

- **JMeter:** 5.6.2  
- **Python:** 3.10+  
- **Bibliotecas:**  
  - `pandas`  
  - `matplotlib`  
  - `reportlab`

---

## 📦 Dependências

Para instalar as dependências necessárias, execute:

```bash
# Clonar o repositório
git clone https://github.com/seu-usuario/fakestore-loadtest.git
cd fakestore-loadtest

# Criar ambiente virtual (opcional)
python -m venv venv
source venv/bin/activate  # ou venv\Scripts\activate no Windows

# Instalar dependências
pip install -r requirements.txt
```

---

## 🧪 Tipo de Teste Realizado

- **Teste de Carga (Load Test)** utilizando Apache JMeter.
- Objetivo: Avaliar a estabilidade e capacidade de resposta do endpoint sob alto volume de requisições simultâneas.
- Métricas validadas:
  - Tempo médio de resposta
  - Tempo máximo de resposta
  - Throughput (req/s)
  - Bytes transferidos
  - Desvio padrão

---

## 🧭 O que foi Validado

- Capacidade do endpoint de suportar **1.800+ requisições/segundo**.  
- Identificação de **picos de latência (até 2.038 ms)**.  
- Consistência do throughput durante o teste.  
- Possíveis pontos de otimização no back-end.

---

## 🧰 Como Executar os Testes Localmente

1. Instale o [Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi).  
2. Abra o arquivo `tests/load_test.jmx` no JMeter.  
3. Ajuste a quantidade de threads/usuários conforme necessário.  
4. Clique em ▶ Start para iniciar o teste.  
5. Após a execução, o arquivo `summary.csv` será gerado em `tests/`.

---

## 📝 Como Gerar o Relatório de Desempenho

Após a execução do teste:

```bash
# Execute o script de geração do relatório
python scripts/gerar_relatorio.py
```

✅ Isso irá gerar automaticamente:
- `reports/Relatorio_FakeStore_API.md`
- `reports/Relatorio_FakeStore_API.pdf`
- Gráficos de latência e throughput

---

## 📊 Exemplo de Métricas Coletadas

| Métrica                   | Valor Médio | Máximo | Throughput (req/s) |
|----------------------------|-------------|--------|---------------------|
| Tempo de resposta (ms)     | 225         | 2038   | 1893,24             |
| Bytes recebidos (KB/s)     | 1878,45     | —      | —                   |
| Bytes enviados (KB/s)      | 284,73      | —      | —                   |

---

## 🚀 Próximos Passos

- Adicionar testes de estresse (Stress Test).  
- Coletar métricas de percentil (P90, P95 e P99).  
- Automatizar execução via CI/CD.  
- Monitoramento contínuo de performance em produção.

---

## 🧑‍💻 Autor

Desenvolvido e mantido por [Seu Nome / Equipe]  
📅 Relatório gerado automaticamente em: {datetime.today().strftime('%d/%m/%Y')}

---

## 📜 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
