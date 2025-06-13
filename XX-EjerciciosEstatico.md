# 04 - Ejercicios Prácticos de Enrutamiento Estático

A continuación se presentan **dos ejercicios completos de enrutamiento estático** al estilo de los exámenes de la Junta de Andalucía.

---

## ✍️ Ejercicio 1: Red de tres oficinas

Una empresa tiene tres oficinas interconectadas mediante routers. Se te proporciona la red principal `192.168.0.0/24`, que debe dividirse para asignar una subred a cada sede y a los enlaces entre routers. 

### Requisitos:

- Red A (Oficina 1): 60 hosts
- Red B (Oficina 2): 30 hosts
- Red C (Oficina 3): 14 hosts
- Se necesitan enlaces punto a punto entre los routers (máximo 2 hosts por enlace)
- Cada sede se conecta a un router (R1, R2, R3). Los routers están conectados entre sí formando un triángulo completo.

### Tareas:

1. Realiza el **subnetting necesario** para cubrir todos los requisitos.
2. Asigna direcciones IP y máscaras a cada interfaz de router y red.
3. Diseña el **esquema de red**.
4. Crea las **tablas de enrutamiento estático** para cada router, indicando:
   - Dirección destino
   - Máscara
   - IP del siguiente salto
   - Interfaz de salida
   - Número de saltos

---

## ✅ Solución resumen:

- Subredes asignadas:
  - Red A: 192.168.0.0/26
  - Red B: 192.168.0.64/27
  - Red C: 192.168.0.96/28
  - Enlaces: 
    - R1-R2: 192.168.0.112/30
    - R2-R3: 192.168.0.116/30
    - R1-R3: 192.168.0.120/30

- Interfaces e IPs:
  - R1: Fa0/0 (Red A), S0/0 (con R2), S0/1 (con R3)
  - R2: Fa0/0 (Red B), S0/0 (con R1), S0/1 (con R3)
  - R3: Fa0/0 (Red C), S0/0 (con R2), S0/1 (con R1)

- Tablas de enrutamiento estático: similares al ejercicio anterior, incluyendo rutas directas y rutas por salto con IPs de vecinos.

---

## ✍️ Ejercicio 2: Campus Universitario

Un campus dispone de tres edificios:
- Administración (50 hosts)
- Aulas (25 hosts)
- Laboratorios (10 hosts)

El administrador de red dispone de la red `10.10.0.0/24` y tres routers interconectados. Los routers forman una línea: R1 ↔ R2 ↔ R3.

### Requisitos:

- Subred para cada edificio
- Enlaces punto a punto entre routers
- Asignación IP
- Tablas de enrutamiento completas

---

## ✅ Solución resumen:

- Subredes asignadas:
  - Administración: 10.10.0.0/26
  - Aulas: 10.10.0.64/27
  - Laboratorios: 10.10.0.96/28
  - Enlaces:
    - R1-R2: 10.10.0.128/30
    - R2-R3: 10.10.0.132/30

- IPs:
  - R1: Fa0/0 (Admin), S0/0 (con R2)
  - R2: Fa0/0 (Aulas), S0/0 (con R1), S0/1 (con R3)
  - R3: Fa0/0 (Labs), S0/0 (con R2)

- Tablas de enrutamiento estático: cada router conoce sus redes directas y las rutas a las otras redes vía saltos intermedios.

---

¿Puedes resolver estos ejercicios por tu cuenta como práctica final del enrutamiento estático?