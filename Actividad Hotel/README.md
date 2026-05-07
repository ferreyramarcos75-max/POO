# Actividad Hotel Polimorfismo

## Clase Main

``` java

public class Hotel {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
       
        AccionHotel accion;
        
        
        accion = new ReservarHabitacion("Habitacion 101",    "Marcos Ferreyra");
        accion.ejecutarAccion();
        
        accion= new Pago("Naranja X",    450000);
        accion.ejecutarAccion();
    }
    
}


````
## Clase Accion Hotel

```` java

public abstract class AccionHotel {
    
    
    
    public abstract void ejecutarAccion ();
}

````

## Clase Reserva Habitacion

```` java

public class ReservarHabitacion extends AccionHotel{

    protected String NumHabit;
    protected String Huesped;

    public ReservarHabitacion(String NumHabit, String Huesped) {
        this.NumHabit = NumHabit;
        this.Huesped = Huesped;
    }

    public String getNumHabit() {
        return NumHabit;
    }

    public void setNumHabit(String NumHabit) {
        this.NumHabit = NumHabit;
    }

    public String getHuesped() {
        return Huesped;
    }

    public void setHuesped(String Huesped) {
        this.Huesped = Huesped;
    }

   
    
    
    @Override
    public void ejecutarAccion() {
   
        System.out.println(this.NumHabit    +    this.Huesped);
    
    
    }
    
}

````

## Clase Pago 

````
public class Pago extends AccionHotel{
    
    protected  String Tarjeta;
    protected int monto;

    public Pago(String Tarjeta, int monto) {
        this.Tarjeta = Tarjeta;
        this.monto = monto;
    }

    public String getTarjeta() {
        return Tarjeta;
    }

    public void setTarjeta(String Tarjeta) {
        this.Tarjeta = Tarjeta;
    }

    public int getMonto() {
        return monto;
    }

    public void setMonto(int monto) {
        this.monto = monto;
    }
    
    
    
    @Override
    public void ejecutarAccion() {
   
        System.out.println(this.Tarjeta   +    this.monto);
    }
    
    
}

````
