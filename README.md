import java.util.Scanner; 
 
interface IConsoles { 
String getConsoleType(); 
String getStore(); 
int getTotalSales(); 
} 
 
abstract class Console implements IConsoles { 
private String consoleType; 
private String store; 
private int totalSales; 
 
public Console(String consoleType, String store, int totalSales) { 
this.consoleType = consoleType; 
this.store = store; 
this.totalSales = totalSales; 
} 
 
public String getConsoleType() { 
return consoleType; 
} 
 
public String getStore() { 
return store; 
} 
 
public int getTotalSales() { 
return totalSales; 
} 
} 
 
class ConsoleSales extends Console { 
 
public ConsoleSales(String consoleType, String store, int totalSales) { 
super(consoleType, store, totalSales); 
} 
 
public void printReport() { 
System.out.println("\n--- Console Sales Report ---"); 
System.out.println("Console Type: " + getConsoleType()); 
System.out.println("Store Name: " + getStore()); 
System.out.println("Total Sales: R" + getTotalSales()); 
} 
} 
 
public class RunApplication { 
public static void main(String[] args) { 
 
Scanner input = new Scanner(System.in); 
 
System.out.println("Select Console Device Type:"); 
System.out.println("1. PlayStation"); 
System.out.println("2. Xbox"); 
System.out.println("3. Nintendo Switch"); 
System.out.print("Enter choice: "); 
 
int choice = input.nextInt(); 
input.nextLine(); 
 
String consoleType; 
 
switch (choice) { 
case 1: 
consoleType = "PlayStation"; 
break; 
case 2: 
consoleType = "Xbox"; 
break; 
case 3: 
consoleType = "Nintendo Switch"; 
break; 
default: 
consoleType = "Unknown"; 
} 
 
System.out.print("Enter store name: "); 
String storeName = input.nextLine(); 
 
System.out.print("Enter total amount of sales: R"); 
int totalSales = input.nextInt(); 
 
ConsoleSales sales = 
new ConsoleSales(consoleType, storeName, totalSales); 
 
sales.printReport(); 
 
input.close(); 
} 
} 
