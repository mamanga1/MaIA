Copiá y pegá este contenido en nano:
markdown
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
- **SO:** Debian 12 Netinstall o superior (consola pura)
- **RAM:** 1GB mínimo (4GB recomendado para enjambre)
- **Herramientas:** Tor, Anonsurf, Nmap, Nikto, Gobuster, Python 3.11+
- **Hardware:** Cualquier netbook, tablet, tvbox recuperada

---

### 🛡️ Fase 1: Blindaje de Red (Anonsurf Nativo)

Para evitar conflictos con repositorios de Kali, compilamos `anonsurf` desde el código fuente original de Rajprins. Esto asegura compatibilidad total con Debian "a guacha pelada".

```bash
# Dependencias base para compilación
sudo apt update && sudo apt install -y git make curl build-essential devscripts

# Clonar y compilar Anonsurf
git clone https://github.com/rajprins/anonsurf.git
cd anonsurf
sudo ./00-install-deps.sh
sudo ./01-package.sh
sudo ./02-install.sh
cd ..
📦 Fase 2: Dependencias de Inteligencia
Instalamos el motor de escaneo y las librerías de Python necesarias para el Enjambre P2P.

bash
# Herramientas de auditoría
sudo apt install -y tor nmap nikto gobuster proxychains4 python3-pip wget curl dnsutils

# Wordlist para gobuster
sudo mkdir -p /usr/share/wordlists/dirb
sudo wget -O /usr/share/wordlists/dirb/common.txt https://raw.githubusercontent.com/danielmiessler/SecLists/master/Discovery/Web-Content/common.txt

# Librerías Python (Debian 12)
pip install --break-system-packages requests[socks] 2>/dev/null || pip install requests[socks] --user
⚙️ Fase 3: Configuración del Sistema
1. Proxychains (Túnel de Emergencia)
Editá /etc/proxychains4.conf y al final agregá:

text
socks5  127.0.0.1 9050
2. Servicios Ocultos (Identidad)
Para que MaIA reciba comandos del enjambre, configurá tu dirección .onion en /etc/tor/torrc:

text
HiddenServiceDir /var/lib/tor/maia/
HiddenServicePort 9876 127.0.0.1:9876
Reiniciá Tor y obtené tu ID:

bash
sudo systemctl restart tor
sudo cat /var/lib/tor/maia/hostname
# Ejemplo: u2e6mrhtz56uq...onion
🚀 Fase 4: Lanzamiento de MaIA
bash
# Clonar el repositorio
git clone https://github.com/mamanga1/MaIA.git
cd MaIA
chmod +x maia install.sh 2>/dev/null

# Instalar
sudo ./install.sh

# Activar anonimato
sudo anonsurf start

# Ejecutar MaIA
maia
🛠️ Guía de Uso Táctico
Comando	Acción
maia	Inicia la interfaz conversacional con la IA
anonimato test	Prueba el funcionamiento de Anonsurf
anonimato activar	Activa Tor + proxychains (IP oculta)
anonimato desactivar	Vuelve a IP real
mi ip	Muestra IP actual
enjambre init	Crea tu servicio oculto Tor y activa tu identidad en la red
enjambre estado	Muestra estado del nodo y peers conocidos
enjambre unirse onion.onion	Conecta a otro nodo del enjambre
enjambre compartir dominio.com 1.2.3.4	Comparte un hallazgo con el enjambre
reputacion	Muestra el ranking de confianza de los nodos conectados
analizar dominio.com	DNS + Cloudflare + subdominios
ipreal dominio.com	Ejecuta el motor de búsqueda de 5 fuentes para saltar Cloudflare
nmap dominio.com	Escaneo rápido
nmapv dominio.com	Escaneo de versiones
nmapfull dominio.com	Escaneo de todos los puertos
nikto dominio.com	Escaneo de vulnerabilidades web
gobuster dominio.com	Escaneo de directorios
!ejecutar [comando]	Ejecuta comandos de sistema a través del blindaje de MaIA
salir	Termina la sesión
📋 Arquitectura del Enjambre
text
┌─────────────────────────────────────────────────────────┐
│                    RED TOR (Onion)                      │
│                                                         │
│   ┌──────────┐      ┌──────────┐      ┌──────────┐     │
│   │ Nodo .248│◄────►│ Nodo .240│◄────►│ Nodo .195│     │
│   │  onion   │      │  onion   │      │  onion   │     │
│   └──────────┘      └──────────┘      └──────────┘     │
│        ▲                  ▲                  ▲         │
│        └──────────────────┴──────────────────┘         │
│                    DHT sobre Tor                        │
└─────────────────────────────────────────────────────────┘
Cada nodo es autónomo pero colaborativo. Si un nodo cae, el enjambre sigue vivo. La comunicación nunca expone IPs reales gracias a los servicios ocultos Tor.

🧪 Ejemplo de Sesión
bash
$ maia

🐝 MaIA v5.20 - MAMANGA INTELLIGENCE ASSISTANT
   Nodo .248 | Corrientes, Argentina
   Soberanía tecnológica o nada. 🧉

💡 Escribí 'ayuda' para ver comandos

Vos 🧉> anonimato test
🧪 TEST DE ANONSURF
IP real: 1.2.3.4
IP Tor: 45.154.98.160
✅ Anonsurf funciona correctamente

Vos 🧉> enjambre init
✅ Servicio oculto activo: 🧅 u2e6mrhtz56uq...onion:9876

Vos 🧉> analizar radi......com
DNS: 208.77.22.107
Cloudflare: NO

Vos 🧉> nmap radio...com
🔍 Escaneo rápido → radios.m.
 ¿Autorizás? (s/n): s
Starting Nmap...
PORT     STATE SERVICE
80/tcp   open  http
443/tcp  open  https
🧉 El Manifiesto del Nodo Corrientes
En un mundo de nubes centralizadas y software privativo, MaIA defiende la autonomía local. Usamos lo que otros tiran para construir lo que otros no pueden controlar.

Hardware Independiente: Netbooks recuperadas.

Software Libre: Python, Tor, Debian.

Mente Abierta: Inteligencia colectiva sin dueños.

Soberanía Tecnológica: Cada nodo es un punto de control autónomo.

📜 Licencia
MIT - Hacé lo que quieras, pero si mejorás algo, compartilo con el enjambre.

🧉 Créditos
Nodo .248 - Corrientes, Argentina

Grok - Inspiración y críticas constructivas

Gemini - Arquitectura P2P y sistema de reputación

MamangaMaster - Desarrollo e integración

Un Mamangá solo es un bicho; un enjambre es una fuerza de la naturaleza que nadie puede apagar. 🐝🚀
