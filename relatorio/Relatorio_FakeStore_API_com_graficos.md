
# 📈 Relatório de Desempenho — FakeStore API

Este documento apresenta a análise de desempenho obtida a partir do arquivo `summary.csv` com base em um teste de carga.

---

## 📊 Resumo Estatístico

| Métrica                  | Valor Médio | Mínimo | Máximo | Desvio Padrão |
|---------------------------|-------------|--------|--------|---------------|
| Amostras (# Samples)       | 796.544     | 796.544 | 796.544 | 0.00          |
| Tempo Médio (ms)           | 225         | 211    | 2.038  | 15.99         |
| Throughput (req/s)         | 1.893,24    | —      | —      | —             |
| Recebido (KB/s)            | 1.878,45    | —      | —      | —             |
| Enviado (KB/s)             | 284,73      | —      | —      | —             |
| Bytes médios por resposta  | 1.016       | —      | —      | —             |

---

## 📉 Gráficos de Desempenho

### ⏱ Latência
![Latência](./latencia_fakestore.png)

### 📡 Throughput
![Throughput](./throughput_fakestore.png)

---

## 🛑 Gargalos Identificados

- Diferença significativa entre tempo **mínimo (211 ms)** e **máximo (2038 ms)** para o endpoint `GET /products/1`.
- Essa variação também se refletiu no **total geral**.

> ⚠️ *Essa diferença sugere picos de latência possivelmente relacionados a sobrecarga no servidor, problemas intermitentes de rede ou ausência de mecanismos de cache adequados.*

---

## 🧭 Oportunidades de Melhoria

1. **Reduzir Picos de Latência**  
   - Implementar cache para requisições frequentes.  
   - Utilizar CDN (Content Delivery Network) para conteúdo estático.

2. **Analisar Requisições Lentas**  
   - Investigar logs de aplicação e banco para identificar causas de latência máxima.

3. **Escalabilidade**  
   - Throughput alto (~1893 req/s) exige infraestrutura elástica para evitar degradação de performance.

4. **Observabilidade**  
   - Adicionar métricas de percentis (P90/P95/P99).  
   - Instrumentar o sistema para localizar gargalos com precisão.

---

## 📌 Recomendações Técnicas Imediatas

- [ ] Configurar alertas para tempos de resposta acima de **1 segundo**.  
- [ ] Ativar logs detalhados e tracing distribuído.  
- [ ] Realizar novos testes de carga com diferentes volumes.  
- [ ] Considerar balanceamento de carga ou replicação do serviço.

---

## 🧪 Próximos Passos (Sugestão)

- Analisar padrões de latência ao longo do tempo.  
- Implementar e monitorar melhorias de cache e CDN.  
- Comparar novos testes de carga após otimizações.

---

> 📅 **Data da análise:** 28/10/2025  
> 🧑 **Autor:** Relatório gerado automaticamente

---

### 📜 Licença

Este relatório pode ser utilizado e adaptado livremente para fins de documentação técnica interna ou pública.
