
# Curso Intensivo de Redes para Oposiciones PES Informática

## 3. Enrutamiento Estático

El enrutamiento estático es una técnica en la que los administradores de red configuran manualmente las rutas en los dispositivos de red. No depende de protocolos de enrutamiento dinámico, lo que le otorga mayor control y predictibilidad, aunque requiere más trabajo de mantenimiento.

### 3.1. Conceptos básicos

- **Router**: dispositivo encargado de enviar paquetes entre redes distintas.
- **Red de destino**: subred a la que se quiere llegar.
- **Máscara o prefijo**: indica el tamaño de la red.
- **IP de siguiente salto (gateway)**: dirección del router vecino al que se debe enviar el paquete.
- **Interfaz de salida**: puerto físico por donde se reenvía el paquete.
- **Métrica o número de saltos**: cantidad de routers intermedios que hay hasta el destino.

### 3.2. Interfaz y asignación de direcciones

Las interfaces se asignan según el tipo de enlace:
- FaX/X para interfaces FastEthernet (LAN).
- SX/X para interfaces Serial (WAN entre routers).

### 3.3. Ejercicio propuesto (esquema en triángulo)

Redes conectadas:
- LAN1: 192.168.1.0/24 conectada a R1
- LAN2: 192.168.2.0/24 conectada a R2
- LAN3: 192.168.3.0/24 conectada a R3
- R1 <-> R2: 10.0.12.0/30
- R2 <-> R3: 10.0.23.0/30

Asignación de interfaces:
- R1: Fa0/0 (LAN1), S0/0 (a R2)
- R2: Fa0/0 (LAN2), S0/0 (a R1), S0/1 (a R3)
- R3: Fa0/0 (LAN3), S0/0 (a R2)

### 3.10. Tablas de enrutamiento por router (formato de examen)

A continuación se presentan las tablas de enrutamiento completas para cada router, en el formato habitual de examen:

#### 🛠 Tabla de enrutamiento de R1

| Dirección destino | Máscara         | IP sig. salto | Interfaz de salida | Nº de saltos |
|-------------------|------------------|----------------|---------------------|---------------|
| 192.168.1.0       | 255.255.255.0     | Directa        | Fa0/0               | 0             |
| 10.0.12.0         | 255.255.255.252   | Directa        | S0/0                | 0             |
| 192.168.2.0       | 255.255.255.0     | 10.0.12.2      | S0/0                | 1             |
| 192.168.3.0       | 255.255.255.0     | 10.0.12.2      | S0/0                | 2             |
| 10.0.23.0         | 255.255.255.252   | 10.0.12.2      | S0/0                | 2             |

#### 🛠 Tabla de enrutamiento de R2

| Dirección destino | Máscara         | IP sig. salto | Interfaz de salida | Nº de saltos |
|-------------------|------------------|----------------|---------------------|---------------|
| 192.168.2.0       | 255.255.255.0     | Directa        | Fa0/0               | 0             |
| 10.0.12.0         | 255.255.255.252   | Directa        | S0/0                | 0             |
| 10.0.23.0         | 255.255.255.252   | Directa        | S0/1                | 0             |
| 192.168.1.0       | 255.255.255.0     | 10.0.12.1      | S0/0                | 1             |
| 192.168.3.0       | 255.255.255.0     | 10.0.23.2      | S0/1                | 1             |

#### 🛠 Tabla de enrutamiento de R3

| Dirección destino | Máscara         | IP sig. salto | Interfaz de salida | Nº de saltos |
|-------------------|------------------|----------------|---------------------|---------------|
| 192.168.3.0       | 255.255.255.0     | Directa        | Fa0/0               | 0             |
| 10.0.23.0         | 255.255.255.252   | Directa        | S0/0                | 0             |
| 192.168.2.0       | 255.255.255.0     | 10.0.23.1      | S0/0                | 1             |
| 192.168.1.0       | 255.255.255.0     | 10.0.23.1      | S0/0                | 2             |
| 10.0.12.0         | 255.255.255.252   | 10.0.23.1      | S0/0                | 2             |
