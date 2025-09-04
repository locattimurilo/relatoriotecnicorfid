# 📡 Relatório Técnico — Investigação de Comunicação de Leitor RFID UHF

## 👋 Introdução
Este relatório documenta a análise e as tentativas de comunicação realizadas com um leitor **RFID UHF**.  

A linha de ação foi:  
1. 📖 Leitura técnica inicial  
2. 🌐 Mapeamento de comunicação e protocolos  
3. 🔍 Descoberta de canais efetivos  
4. 🛠️ Tentativas práticas de comunicação  

---

## ⚙️ Especificações Técnicas

- **Chip RF:** Impinj E710  
- **Frequências de Operação:**  
  - Europa: 865–868 MHz  
  - Américas: 902–928 MHz  
  - Ásia: 920–925 MHz  
- **Potência RF:** 0 a 30 dBm  
- **Distância de leitura:** até 10 m (dependente da antena e ambiente)  
- **Protocolos suportados:** EPC CLASS1 G2, ISO18000-6C, ISO18000-6B  
- **Interfaces de comunicação:** RS232, RS485, TCP/IP (RJ45)  
- **Entradas e saídas:** GPIO, Wiegand 26/34 bits  
- **Alimentação:** 12V/3A ou PoE  

---

## 🛠️ Ambiente e Ferramentas

- Conexão via **cabo RJ45** (IP fixo em rede local isolada)  
- **Wi-Fi** mantido para acesso à internet paralelo  
- Ferramentas utilizadas:  
  - 🔎 `nmap` (varredura UDP)  
  - 📡 `tcpdump` / `Wireshark` (captura e inspeção de pacotes)  
  - 🌍 `arp-scan` (descoberta via MAC/IP)  
  - 🐍 Script próprio em **Python** para discovery, sniffing e tentativa de decode de EPCs  

---

## 🔬 Metodologia e Execução

### 🔍 Descoberta de dispositivo e fingerprint
- Dispositivo emitiu **broadcasts UDP periódicos (~3s)**  
- Origem: **porta 1969/UDP**  
- Destino: **255.255.255.255:4444**  
- Payloads constantes de **20 bytes** → comportamento típico de **beacon/heartbeat**  

LER APENDICES PARA VER CAPTURAS


