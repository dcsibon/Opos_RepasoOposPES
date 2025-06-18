
# Chuleta Java Básico + Intermedio (PES Informática)

---

## 1. Estructura básica

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hola Mundo");
    }
}
```

---

## 2. Variables y tipos de datos

```java
int x = 5;
double y = 3.14;
boolean activo = true;
char letra = 'A';
String texto = "Hola";
```

---

## 3. Operadores

```java
+  -  *  /  %
== != > < >= <=
&& || !
```

---

## 4. Estructuras de control

### If / Else

```java
if (x > 0) {
    System.out.println("Positivo");
} else {
    System.out.println("Negativo o cero");
}
```

### Switch

```java
switch (opcion) {
    case 1:
        ...
        break;
    default:
        ...
}
```

### For

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

### While

```java
while (x > 0) {
    x--;
}
```

### Do While

```java
do {
    x--;
} while (x > 0);
```

---

## 5. Métodos

```java
public static int sumar(int a, int b) {
    return a + b;
}
```

---

## 6. Arrays

```java
int[] numeros = {1, 2, 3, 4};
String[] nombres = new String[5];
nombres[0] = "Ana";
```

---

## 7. Clases y Objetos

```java
public class Persona {
    String nombre;
    int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public void saludar() {
        System.out.println("Hola, soy " + nombre);
    }
}

Persona p = new Persona("Luis", 30);
p.saludar();
```

---

## 8. Encapsulamiento (getters/setters)

```java
private String nombre;

public String getNombre() {
    return nombre;
}

public void setNombre(String nombre) {
    this.nombre = nombre;
}
```

---

## 9. Herencia

```java
public class Animal {
    public void sonido() {
        System.out.println("Sonido de animal");
    }
}

public class Perro extends Animal {
    public void sonido() {
        System.out.println("Guau");
    }
}

Animal miAnimal = new Perro();
miAnimal.sonido(); // Guau (polimorfismo)
```

---

## 10. Interfaces

```java
public interface Volador {
    void volar();
}

public class Pajaro implements Volador {
    public void volar() {
        System.out.println("Pájaro volando");
    }
}
```

---

## 11. Clases abstractas

```java
public abstract class Figura {
    abstract double area();
}
```

---

## 12. Colecciones (List, Set, Map)

### List

```java
List<String> lista = new ArrayList<>();
lista.add("uno");
lista.add("dos");

for (String s : lista) {
    System.out.println(s);
}
```

### Set

```java
Set<String> conjunto = new HashSet<>();
conjunto.add("A");
conjunto.add("B");
```

### Map

```java
Map<Integer, String> mapa = new HashMap<>();
mapa.put(1, "uno");
mapa.put(2, "dos");

for (Map.Entry<Integer, String> entry : mapa.entrySet()) {
    System.out.println(entry.getKey() + ": " + entry.getValue());
}
```

---

## 13. Excepciones

```java
try {
    int r = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Error: " + e.getMessage());
} finally {
    System.out.println("Fin del try-catch");
}
```

---

## 14. Entrada por teclado

```java
Scanner sc = new Scanner(System.in);
System.out.print("Introduce un número: ");
int num = sc.nextInt();
System.out.println("Has introducido: " + num);
```

---

## 15. String

```java
String s = "Hola";
System.out.println(s.length());
System.out.println(s.toUpperCase());
System.out.println(s.substring(0, 2));
```

---

## 16. ForEach y Lambda

```java
List<String> lista = Arrays.asList("uno", "dos", "tres");
lista.forEach( s -> System.out.println(s) );
```

---

## 17. Buenas prácticas

- Nombres descriptivos
- Comentarios útiles
- Principio de responsabilidad única
- Usar clases e interfaces para organizar el código
- Manejar siempre las excepciones
- Usar colecciones según necesidad (List, Set, Map)
- No abusar de variables globales
- Separar lógica de negocio y presentación

---
