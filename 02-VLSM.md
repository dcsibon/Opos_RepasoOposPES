
# Curso Intensivo de Redes para Oposiciones PES Informática

## 2. VLSM (Variable Length Subnet Masking)

Permite dividir una red grande en subredes de distintos tamaños, aprovechando mejor el espacio de direcciones.

### 🧪 Ejercicio 2 – VLSM tipo examen

**Se dispone de la red 192.168.100.0/24. Se requieren subredes para:**

| Red    | Nº Hosts |
|--------|----------|
| LAN_A  | 60       |
| LAN_B  | 30       |
| LAN_C  | 12       |
| LAN_D  | 6        |
| LAN_E  | 2        |

**Objetivo:** Asignar subredes sin solapamientos.

---

### Cálculos previos:

| LAN   | Hosts | Bloque | Bits Host | CIDR | Máscara Decimal   |
|-------|-------|--------|-----------|------|--------------------|
| A     | 60    | 64     | 6         | /26  | 255.255.255.192    |
| B     | 30    | 32     | 5         | /27  | 255.255.255.224    |
| C     | 12    | 16     | 4         | /28  | 255.255.255.240    |
| D     | 6     | 8      | 3         | /29  | 255.255.255.248    |
| E     | 2     | 4      | 2         | /30  | 255.255.255.252    |

---

### Asignación de subredes:

| LAN   | Red                | Rango válido              | Broadcast           |
|-------|--------------------|----------------------------|----------------------|
| A     | 192.168.100.0/26   | 192.168.100.1 – 62         | 192.168.100.63       |
| B     | 192.168.100.64/27  | 192.168.100.65 – 94        | 192.168.100.95       |
| C     | 192.168.100.96/28  | 192.168.100.97 – 110       | 192.168.100.111      |
| D     | 192.168.100.112/29 | 192.168.100.113 – 118      | 192.168.100.119      |
| E     | 192.168.100.120/30 | 192.168.100.121 – 122      | 192.168.100.123      |

---

**Resumen final para examen:**

```
LAN_A: 192.168.100.0/26 – 255.255.255.192
→ Rango válido: 192.168.100.1 – 192.168.100.62
→ Broadcast: 192.168.100.63

LAN_B: 192.168.100.64/27 – 255.255.255.224
→ Rango válido: 192.168.100.65 – 192.168.100.94
→ Broadcast: 192.168.100.95

LAN_C: 192.168.100.96/28 – 255.255.255.240
→ Rango válido: 192.168.100.97 – 192.168.100.110
→ Broadcast: 192.168.100.111

LAN_D: 192.168.100.112/29 – 255.255.255.248
→ Rango válido: 192.168.100.113 – 192.168.100.118
→ Broadcast: 192.168.100.119

LAN_E: 192.168.100.120/30 – 255.255.255.252
→ Rango válido: 192.168.100.121 – 192.168.100.122
→ Broadcast: 192.168.100.123
```
