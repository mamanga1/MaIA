# 🐝 MaIA v5.20 - MAMANGA INTELLIGENCE ASSISTANT

> **"Soberanía tecnológica o nada."** 🧉🚀  
> Proyecto nacido en el Nodo .248 | Corrientes, Argentina.

MaIA (Mamanga Intelligence Assistant) no es solo un script; es un **sistema inmunológico digital distribuido**. Diseñada para correr en hardware de bajos recursos (Netbooks con 1GB RAM, Celeron, Debian), transforma máquinas "obsoletas" en nodos de una red de inteligencia y auditoría técnica de alta resiliencia.

---

## 🛡️ Pilares del Proyecto

### 1. Anonimato de Grado Militar
Integración nativa con **Anonsurf, Tor y Proxychains**. MaIA nunca expone la IP real del nodo. Cada consulta, escaneo o comunicación P2P viaja encriptada y ruteada por circuitos cebolla.

### 2. Enjambre P2P y Reputación Asimétrica
Los nodos no confían ciegamente. MaIA implementa un **Sistema de Reputación Asimétrica**:
- **Aporte Válido (+10):** El nodo comparte un hallazgo verificado.
- **Error/Honeypot (-25):** El sistema penaliza fuertemente los datos falsos para proteger al enjambre de intrusos.

### 3. Escaneo Distribuido
¿Un escaneo `nmap --full` tarda mucho en una netbook? Con el comando `enjambre escanear`, el trabajo se fragmenta entre todos los nodos activos del enjambre, unificando resultados al finalizar.

---

## 🚀 Instalación y Despliegue

### Requisitos Mínimos
- **SO:** Debian 12 o superior (netinstall consola a guacha pelada)
- **RAM:** 1GB mínimo (4GB recomendado para enjambre)
- **Herramientas:** Tor, Anonsurf, Nmap, Nikto, Gobuster, Python 3.11+
- **Hardware:** Cualquier netbook recuperada

### Setup Rápido
```bash
git clone https://github.com/MamangaMaster/MaIA.git
cd MaIA
chmod +x install.sh
sudo ./install.sh
