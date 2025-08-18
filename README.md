
## 🔭 **Prometheus and Grafana**  
Prometheus is a monitoring system that specializes in collecting and storing time-series data. It operates by *scraping* metrics from configured targets (e.g., servers, applications, databases) at specified intervals.  

- ⚙️ Prometheus architecture contains **master and node** components.  
- 📡 It follows a **pull model** and stores data in a **time-series database**.  
- 🔄 The Prometheus server periodically **pulls metrics** from nodes.  
- 🖥️ **Node Exporter** runs on servers as an agent to collect metrics.  

### Monitoring Flow  
👤 **User** → 📊 **Prometheus Server** → 🖥️ **Node Exporter (Nodes)**  

### Components inside Prometheus Server  
- 🌐 **HTTP Server (Browser UI)**  
- 🗄️ **Time-Series Database**  
- 🚨 **Alertmanager**  
- 🔍 **Service Discovery**  
- 📈 **Grafana (Visualization)**  

---

## 📊 **Dashboard**  
A **dashboard** is a web-based application that provides a summarized view of key service metrics.  
- 🎛️ Preconfigured to show **important KPIs**  
- 🔍 Allows **filters and selectors** for deeper analysis  
- 📌 Displays both **performance data** and **operational details** (e.g., ticket queues, high-priority issues, on-call engineer, recent deployments)  

---

## 🚨 **Alert**  
An **alert** is a notification that requires human attention. It is automatically routed to systems such as:  
- 📝 **Ticketing system** → creates support/incident tickets  
- 📧 **Email alias** → sends notifications to teams  
- 📟 **Pager/on-call system** → triggers immediate action  

---

## 🛠️ **Root Cause**  
The **root cause** is the fundamental defect in software, process, or human action that leads to an incident. Fixing it ensures the issue doesn’t repeat.  

Examples:  
- ⚡ Inadequate automation processes  
- 💥 Application crashes on invalid input  
- 🧪 Insufficient testing of configuration scripts  

---

## 🌟 **The Four Golden Signals of Monitoring**  

### ⏱️ 1. Latency  
- Measures how long requests take.  
- Differentiate between **successful latency** and **error latency**.  
- 🐢 Slow errors are worse than fast errors.  

---

### 📡 2. Traffic  
- Represents demand on the system.  
- 🌍 Web services → HTTP requests/sec  
- 🎵 Streaming → Network I/O or sessions  
- 🗄️ Databases → Transactions/sec  

---

### ❌ 3. Errors  
- Explicit → 🚫 HTTP 500  
- Implicit → ⚠️ HTTP 200 with wrong data  
- Policy-based → ⏳ Requests slower than SLA  

Load balancers catch most failures, but **end-to-end checks** detect hidden issues.  

---

### 📉 4. Saturation  
- Shows how “full” your system is (CPU, memory, I/O).  
- ⚠️ Performance drops *before* 100% usage.  
- Key indicators:  
  - 🖥️ CPU/Network nearing limits  
  - 💾 Storage filling up  
  - ⏱️ 99th percentile latency rising  
- 🔮 Includes forecasting (e.g., database will fill disk in 4 hrs).  

---

👉 **Best Practice**: Monitor all **four golden signals** and trigger alerts when thresholds are breached (or nearly breached) to maintain service reliability.  
