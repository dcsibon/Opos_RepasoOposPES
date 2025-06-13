# 03 - Enrutamiento Estático

## 10. Tablas de enrutamiento por router (formato de examen)

A continuación se presentan las tablas de enrutamiento completas para cada router, en el formato habitual de examen:

---

### 🛠 Tabla de enrutamiento de R1

| Dirección destino | Máscara           | IP sig. salto | Interfaz de salida | Nº de saltos |
|-------------------|-------------------|----------------|---------------------|--------------|
| 192.168.1.0        | 255.255.255.0     | Directa        | Fa0/0               | 0            |
| 10.0.12.0          | 255.255.255.252   | Directa        | S0/0                | 0            |
| 192.168.2.0        | 255.255.255.0     | 10.0.12.2      | S0/0                | 1            |
| 192.168.3.0        | 255.255.255.0     | 10.0.12.2      | S0/0                | 2            |
| 10.0.23.0          | 255.255.255.252   | 10.0.12.2      | S0/0                | 2            |

---

### 🛠 Tabla de enrutamiento de R2

| Dirección destino | Máscara           | IP sig. salto | Interfaz de salida | Nº de saltos |
|-------------------|-------------------|----------------|---------------------|--------------|
| 192.168.2.0        | 255.255.255.0     | Directa        | Fa0/0               | 0            |
| 10.0.12.0          | 255.255.255.252   | Directa        | S0/0                | 0            |
| 10.0.23.0          | 255.255.255.252   | Directa        | S0/1                | 0            |
| 192.168.1.0        | 255.255.255.0     | 10.0.12.1      | S0/0                | 1            |
| 192.168.3.0        | 255.255.255.0     | 10.0.23.2      | S0/1                | 1            |

---

### 🛠 Tabla de enrutamiento de R3

| Dirección destino | Máscara           | IP sig. salto | Interfaz de salida | Nº de saltos |
|-------------------|-------------------|----------------|---------------------|--------------|
| 192.168.3.0        | 255.255.255.0     | Directa        | Fa0/0               | 0            |
| 10.0.23.0          | 255.255.255.252   | Directa        | S0/0                | 0            |
| 192.168.2.0        | 255.255.255.0     | 10.0.23.1      | S0/0                | 1            |
| 192.168.1.0        | 255.255.255.0     | 10.0.23.1      | S0/0                | 2            |
| 10.0.12.0          | 255.255.255.252   | 10.0.23.1      | S0/0                | 2            |