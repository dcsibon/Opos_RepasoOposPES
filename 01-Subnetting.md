
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

---

### 🧪 Ejercicio 1 – Básico de Subnetting

**Dada la dirección IP 10.0.0.77/28, se pide:**
- Dirección de red
- Primera IP válida
- Última IP válida
- Dirección de broadcast
- Máscara decimal

**Resolución:**
- Bits de host: 32 - 28 = 4 → 2⁴ = 16 direcciones → bloques de 16 en 4º octeto
- Subredes posibles: 10.0.0.0, 10.0.0.16, ..., 10.0.0.64, 10.0.0.80
- 10.0.0.77 ∈ [10.0.0.64/28]

**Resultado:**
- Red: 10.0.0.64
- Primera IP válida: 10.0.0.65
- Última IP válida: 10.0.0.78
- Broadcast: 10.0.0.79
- Máscara: 255.255.255.240

---
