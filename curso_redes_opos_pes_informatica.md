
# Curso Intensivo de Redes para Oposiciones PES Informática

## 1. Subnetting IPv4 – Fundamentos

### ¿Qué es una dirección IP?

Una dirección IPv4 se compone de 4 bloques decimales separados por puntos, por ejemplo:
```
192.168.1.10
```
Cada bloque representa 8 bits (octeto), totalizando 32 bits.

### ¿Qué es una máscara de subred?

Indica cuántos bits están reservados para la parte de red. Ejemplos comunes:

| CIDR | Máscara Decimal     | Bits de Red | Bits de Host | Hosts Útiles |
|------|----------------------|-------------|--------------|--------------|
| /24  | 255.255.255.0        | 24          | 8            | 254          |
| /26  | 255.255.255.192      | 26          | 6            | 62           |
| /30  | 255.255.255.252      | 30          | 2            | 2            |

> Fórmula para calcular hosts útiles:  
> `2^n - 2` donde `n` son los bits de host.

### Ejemplo: IP 10.0.0.77/28

1. 32 - 28 = 4 bits para host → 2⁴ = 16 → Bloque de 16 direcciones  
2. Subredes posibles: 10.0.0.0, 10.0.0.16, ..., 10.0.0.64, 10.0.0.80  
3. 10.0.0.77 pertenece a subred 10.0.0.64/28

**Resultado:**
- Red: 10.0.0.64
- Primera IP válida: 10.0.0.65
- Última IP válida: 10.0.0.78
- Broadcast: 10.0.0.79
- Máscara: 255.255.255.240

---

## 2. VLSM (Variable Length Subnet Masking)

Permite dividir una red grande en subredes de distintos tamaños, aprovechando mejor el espacio de direcciones.

### Ejemplo:

Red base: `192.168.100.0/24`  
Requisitos:

| LAN   | Hosts Necesarios |
|-------|------------------|
| A     | 60               |
| B     | 30               |
| C     | 12               |
| D     | 6                |
| E     | 2                |

### Cálculos:

| LAN   | Hosts | Bloque | Bits Host | CIDR | Máscara Decimal   |
|-------|-------|--------|-----------|------|--------------------|
| A     | 60    | 64     | 6         | /26  | 255.255.255.192    |
| B     | 30    | 32     | 5         | /27  | 255.255.255.224    |
| C     | 12    | 16     | 4         | /28  | 255.255.255.240    |
| D     | 6     | 8      | 3         | /29  | 255.255.255.248    |
| E     | 2     | 4      | 2         | /30  | 255.255.255.252    |

### Asignación de subredes:

| LAN   | Red                | Rango válido              | Broadcast           |
|-------|--------------------|----------------------------|----------------------|
| A     | 192.168.100.0/26   | 192.168.100.1 – 62         | 192.168.100.63       |
| B     | 192.168.100.64/27  | 192.168.100.65 – 94        | 192.168.100.95       |
| C     | 192.168.100.96/28  | 192.168.100.97 – 110       | 192.168.100.111      |
| D     | 192.168.100.112/29 | 192.168.100.113 – 118      | 192.168.100.119      |
| E     | 192.168.100.120/30 | 192.168.100.121 – 122      | 192.168.100.123      |
