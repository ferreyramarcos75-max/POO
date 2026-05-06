# Solucion Actividad N 7

## Clase Persona

``` java 
public class Persona {
    private String nombre;
    private String dni;
    
    public Persona(String nombre, String dni) {
        this.nombre = nombre;
        this.dni = dni;
    }
    
    public String getNombre() { return nombre; }
    public String getDni() { return dni; }
    
    @Override
    public String toString() {
        return nombre + " (DNI: " + dni + ")";
    }
}

```

## Clase Vehiculo

``` java

public abstract class Vehiculo {
    
    protected String marca;
    protected String modelo;
    protected double precio;
    
    public Vehiculo(String marca, String modelo, double precio) {
        this.marca = marca;
        this.modelo = modelo;
        this.precio = precio;
    }
    
   
    public abstract void mostrarDetalles();
    
    public String getMarca() { return marca; }
    public String getModelo() { return modelo; }
    public double getPrecio() { return precio; }
    
}

```

## Clase Venta

``` java

public class Venta {
    
     private Persona vendedor;
    private Persona comprador;
    private Vehiculo vehiculo;
    private static int contadorFacturas = 0;
    private int numeroFactura;
    
    public Venta(Persona vendedor, Persona comprador, Vehiculo vehiculo) {
        this.vendedor = vendedor;
        this.comprador = comprador;
        this.vehiculo = vehiculo;
        this.numeroFactura = ++contadorFacturas;
    }
    
    public void imprimirFactura() {
        System.out.println("FACTURA N°: " + numeroFactura);
        System.out.println("----------------------");
        System.out.println("VENDEDOR: " + vendedor);
        System.out.println("COMPRADOR: " + comprador);
        System.out.println("----------------------");
        System.out.println("VEHÍCULO VENDIDO:");
        vehiculo.mostrarDetalles();  

        System.out.println("----------------------");
        System.out.println("TOTAL: $" + vehiculo.getPrecio());
    }
}

```

## Clase Auto

``` java

public class  Auto extends  Vehiculo{

     private int cantidadPuertas;
    
    public Auto(String marca, String modelo, double precio, int cantidadPuertas) {
        super(marca, modelo, precio);
        this.cantidadPuertas = cantidadPuertas;
    }
    
    @Override
    public void mostrarDetalles() {
        System.out.println("Auto: " + marca + " " + modelo + 
                         " | Puertas: " + cantidadPuertas + 
                         " | Precio: $" + precio);
    }
    
}

```

## Clase Moto

 ``` java

 public class Moto extends Vehiculo{

   private int cilindrada;
    
    public Moto(String marca, String modelo, double precio, int cilindrada) {
        super(marca, modelo, precio);
        this.cilindrada = cilindrada;
    }
    
    @Override
    public void mostrarDetalles() {
        System.out.println("Moto: " + marca + " " + modelo + 
                         " | Cilindrada: " + cilindrada + "cc" +
                         " | Precio: $" + precio);
    }
    
}

```
## Main

``` java

public static void main(String[] args) {
        
        
        Persona vendedor = new Persona("Marcos Antonio", "45262145");
        Persona comprador = new Persona("Figueroa Ignacio", "40111222");

       
        Vehiculo auto1 = new Auto("Ford", "RAM", 33000000, 4);
        Vehiculo moto1 = new Moto("Honda", "Wavw NF 100", 540000, 100);

       
        Venta factura1 = new Venta(vendedor, comprador, auto1);

        System.out.println("--- Procesando Venta de Concesionaria ---");
        factura1.imprimirFactura();        
        System.out.println("\n------------------------------------------");
        

        Venta factura2 = new Venta(vendedor, comprador, moto1);
        factura2.imprimirFactura();
               
    }
    
    