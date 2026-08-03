# QA Agibank - Testes de Performance

Este repositório contém o plano de testes de performance desenvolvido em **Apache JMeter 5.5** para o desafio.

---

## 🎯 Objetivo
Validar o fluxo de compra de passagens no site [BlazeDemo](https://www.blazedemo.com) sob diferentes cenários de carga e pico, garantindo estabilidade, tempo de resposta adequado e baixa taxa de erros.

---

## 📂 Estrutura do Repositório
- `QA-agibank-performance.jmx` → Plano de teste JMeter
- `dados.txt` → Massa de dados parametrizada (origem, destino, dados de cartão)
- `README.md` → Documentação

---

## 🧪 Cenários de Teste
- **Carga**  
  - 250 usuários  
  - Ramp-up: 50 segundos  
  - Objetivo: validar estabilidade sob uso normal

- **Pico**  
  - 500 usuários  
  - Ramp-up: 10 segundos  
  - Objetivo: validar comportamento sob estresse

- **Fluxo completo testado**  
  1. Reserva de voo (`/reserve.php`)  
  2. Escolha do voo (`/purchase.php`)  
  3. Confirmação da compra (`/confirmation.php`)

---

## 📊 Métricas coletadas
- **Throughput** (requisições por segundo)  
- **Latência média**  
- **Percentis** (90º, 95º, 99º)  
- **Taxa de erros**  

---

## 🚀 Como executar
1. Instale [Apache JMeter 5.5](https://jmeter.apache.org/).  
2. Abra o arquivo `QA-agibank-performance.jmx`.  
3. Ajuste o caminho do `dados.txt` no CSV Data Set Config.  
4. Execute os Thread Groups separadamente (Carga e Pico).  
5. Gere relatórios HTML com o comando:
   ```bash
   jmeter -n -t QA-agibank-performance.jmx -l results.jtl -e -o report
