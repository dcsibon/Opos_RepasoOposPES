
# Ejemplo tipo PES: Gestión de Biblioteca en Java

Ejemplo práctico de supuestos típicos en examen: gestión de elementos con POO + Colecciones + Scanner + Menú + Excepciones.

---

## Main.java

```java
import java.util.*;

public class Main {

    static Scanner sc = new Scanner(System.in);
    static List<Libro> libros = new ArrayList<>();
    static List<Usuario> usuarios = new ArrayList<>();

    public static void main(String[] args) {

        int opcion;
        do {
            mostrarMenu();
            opcion = pedirEntero("Elige opción: ");

            switch (opcion) {
                case 1 -> agregarLibro();
                case 2 -> listarLibros();
                case 3 -> agregarUsuario();
                case 4 -> listarUsuarios();
                case 5 -> buscarLibroPorTitulo();
                case 0 -> System.out.println("Saliendo...");
                default -> System.out.println("Opción no válida.");
            }
        } while (opcion != 0);
    }

    static void mostrarMenu() {
        System.out.println("\n=== MENÚ BIBLIOTECA ===");
        System.out.println("1. Agregar libro");
        System.out.println("2. Listar libros");
        System.out.println("3. Agregar usuario");
        System.out.println("4. Listar usuarios");
        System.out.println("5. Buscar libro por título");
        System.out.println("0. Salir");
    }

    static void agregarLibro() {
        System.out.print("Título: ");
        String titulo = sc.nextLine();

        System.out.print("Autor: ");
        String autor = sc.nextLine();

        int anio = pedirEntero("Año publicación: ");

        libros.add(new Libro(titulo, autor, anio));
        System.out.println("Libro agregado.");
    }

    static void listarLibros() {
        if (libros.isEmpty()) {
            System.out.println("No hay libros.");
        } else {
            System.out.println("\n--- LIBROS ---");
            libros.forEach(l -> System.out.println(l));
        }
    }

    static void agregarUsuario() {
        System.out.print("Nombre: ");
        String nombre = sc.nextLine();

        System.out.print("Email: ");
        String email = sc.nextLine();

        usuarios.add(new Usuario(nombre, email));
        System.out.println("Usuario agregado.");
    }

    static void listarUsuarios() {
        if (usuarios.isEmpty()) {
            System.out.println("No hay usuarios.");
        } else {
            System.out.println("\n--- USUARIOS ---");
            usuarios.forEach(u -> System.out.println(u));
        }
    }

    static void buscarLibroPorTitulo() {
        System.out.print("Introduce título a buscar: ");
        String titulo = sc.nextLine();

        boolean encontrado = false;
        for (Libro l : libros) {
            if (l.getTitulo().equalsIgnoreCase(titulo)) {
                System.out.println("Encontrado: " + l);
                encontrado = true;
            }
        }

        if (!encontrado) {
            System.out.println("Libro no encontrado.");
        }
    }

    static int pedirEntero(String mensaje) {
        int num = -1;
        boolean valido = false;

        while (!valido) {
            try {
                System.out.print(mensaje);
                num = Integer.parseInt(sc.nextLine());
                valido = true;
            } catch (NumberFormatException e) {
                System.out.println("Número no válido. Intenta de nuevo.");
            }
        }
        return num;
    }
}
```

---

## Libro.java

```java
public class Libro {
    private String titulo;
    private String autor;
    private int anio;

    public Libro(String titulo, String autor, int anio) {
        this.titulo = titulo;
        this.autor = autor;
        this.anio = anio;
    }

    public String getTitulo() {
        return titulo;
    }

    @Override
    public String toString() {
        return titulo + " - " + autor + " (" + anio + ")";
    }
}
```

---

## Usuario.java

```java
public class Usuario {
    private String nombre;
    private String email;

    public Usuario(String nombre, String email) {
        this.nombre = nombre;
        this.email = email;
    }

    @Override
    public String toString() {
        return nombre + " <" + email + ">";
    }
}
```

---

## Qué muestra este ejemplo

- Programación orientada a objetos (POO)
- Uso de ArrayList
- Menú interactivo con Scanner
- Manejo de excepciones (try-catch)
- Métodos auxiliares
- Separación de clases
- Uso de `forEach`

Perfecto como plantilla de supuestos tipo PES para examen de Programación en Java.

---
