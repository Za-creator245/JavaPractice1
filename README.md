# JavaPractice1
Write a Java program with a base class Appliance (applianceId, brand) and a method calculatePowerConsumption() which is overridden in WashingMachine (powerPerCycle, cyclesUsed) to return powerPerCycle × cyclesUsed and in Refrigerator (powerPerDay, daysUsed) to return powerPerDay × daysUsed. Both subclasses also overload calculatePowerConsumption() to accept a reduction percentage and return the reduced consumption. In the main method, create objects of WashingMachine and Refrigerator, call both versions of the method, and display the results to illustrate inheritance, method overriding, and overloading. Write down in 4 different class files and the Attributes of Appliance are ApplianceID, Brand, CalculatePowerConsumption (), powerCycle, CycleUsed, CalculatePowerConsumption () for Washingmachine, and last but not the list, PowerCycle, daysused, CalculatePowerConsumption() for Refrigerator. 

Answer : 

Number 1 Class :
public class Appliance {
    protected int applianceId;
    protected String brand;

    // Constructor
    
    public Appliance(int applianceId, String brand) {
        this.applianceId = applianceId;
        this.brand = brand;
    }

    // Method to be overridden
    public double calculatePowerConsumption() {
        return 0.0; // Default implementation
    }
}

Number2 Class :

public class WashingMachine extends Appliance {
    private double powerPerCycle;
    private int cyclesUsed;

    // Constructor
    public WashingMachine(int applianceId, String brand, double powerPerCycle, int cyclesUsed) {
        super(applianceId, brand);
        this.powerPerCycle = powerPerCycle;
        this.cyclesUsed = cyclesUsed;
    }

    // Overridden method
    @Override
    public double calculatePowerConsumption() {
        return powerPerCycle * cyclesUsed;
    }

    // Overloaded method with reduction percentage
    public double calculatePowerConsumption(double reductionPercent) {
        double consumption = calculatePowerConsumption();
        return consumption - (consumption * reductionPercent / 100);
    }
}


Number 3 Class :

public class Refrigerator extends Appliance {
    private double powerPerDay;
    private int daysUsed;

    // Constructor
    public Refrigerator(int applianceId, String brand, double powerPerDay, int daysUsed) {
        super(applianceId, brand);
        this.powerPerDay = powerPerDay;
        this.daysUsed = daysUsed;
    }

    // Overridden method
    @Override
    public double calculatePowerConsumption() {
        return powerPerDay * daysUsed;
    }

    // Overloaded method with reduction percentage
    public double calculatePowerConsumption(double reductionPercent) {
        double consumption = calculatePowerConsumption();
        return consumption - (consumption * reductionPercent / 100);
    }
}


Number 4 Class :

public class MainApp {
    public static void main(String[] args) {
        // Create Washing Machine object
        WashingMachine wm = new WashingMachine(101, "LG", 1.5, 30);
        System.out.println("Washing Machine Power Consumption (normal): " + wm.calculatePowerConsumption() + " kWh");
        System.out.println("Washing Machine Power Consumption (with 10% reduction): " + wm.calculatePowerConsumption(10) + " kWh");

        System.out.println();

        // Create Refrigerator object
        Refrigerator fridge = new Refrigerator(202, "Samsung", 2.0, 15);
        System.out.println("Refrigerator Power Consumption (normal): " + fridge.calculatePowerConsumption() + " kWh");
        System.out.println("Refrigerator Power Consumption (with 20% reduction): " + fridge.calculatePowerConsumption(20) + " kWh");
    }
}









