package BuyCodes;



import java.util.*;


public class format {
	
	static String country;
	static int choose,adultQty,childQty,adultPrice,adultTotal,childPrice,subTotal,discount,total;
	static Scanner enter = new Scanner(System.in);
	
	public static void main(String args[]) {
		
		char again;
			
		do {
			
		PackageMenu();
		
		System.out.print("\n\n Do you want to Try again? y/n ");
		again = enter.next().charAt(0);
		  
		} while (again == 'y' || again=='Y');
		
	}	//main
	
	static void PackageMenu() {
	String Receipt="";

		System.out.format("\n %-20s %-10s %s\n","Country","Adult","Child");
		System.out.format("\n  %-20s %-10d %d","Philippines",100,50);
		System.out.format("\n  %-20s %-10s %s","Korea", 100,50);
		System.out.format("\n  %-20s %-10s %s","Japan",100,50);
		System.out.format("\n  %-20s \n","Exit",100,50);

		while(true) {
		choose = Scan(enter, "\n Choose Package: ");
		
		if(choose>5) {
			System.out.println(" out of Range");
		} else break;
		
		}
	
		adultQty = Scan(enter, "\n adultQuantity: ");
		childQty = Scan(enter, "\n childQuantity: ");
		
		switch(choose) {
		case 1: 
				country = " Philippines";
				adultPrice = 100;
				adultTotal = adultPrice * adultQty;
				
				childPrice = 50;
				if(childPrice>=0) {
				subTotal = childPrice * childQty;
				discount = (subTotal * 10) /100;
				total = subTotal - discount;
				}
				break;
		case 2: 
			 country = " Korea";
			 adultPrice = 100;
				adultTotal = adultPrice * adultQty;
				
				childPrice = 50;
				if(childPrice>=0) {
				subTotal = childPrice * childQty;
				discount = (subTotal * 10) /100;
				total = subTotal - discount;
				}
				break;
		case 3: 
			country = " Japan";
			adultPrice = 100;
			adultTotal = adultPrice * adultQty;
			
			childPrice = 50;
			if(childPrice>=0) {
			subTotal = childPrice * childQty;
			discount = (subTotal * 10) /100;
			total = subTotal - discount;
			}
			break;
		case 4: 
			System.exit(0);
			break;
		}	//choose
		
			//Receipt
		System.out.print("\n\t Receipt - Title");
    System.out.print(receipt(Receipt));
		
		
		
	}	//PackageMenu
	
	static int Scan(Scanner console,String Deter) {
		String Str;
		int TryOrCatch = -1;
		
		while(TryOrCatch < 0) {
			System.out.print(Deter);
			Str = enter.nextLine();
			
			try {
				TryOrCatch = Integer.parseInt(Str);
			} catch (NumberFormatException e) {				
				System.out.print(" Please Input valid Character! \n");
			}
			
		}	//while
		return TryOrCatch;
	}	//Choose
	
	static String receipt(String Receipt) {
     Receipt += "\n";
		Receipt += "Country: " + country;
		Receipt += "\nAdult Quantity: " + adultQty;
		Receipt += "\nChild Quantity: " + childQty;
		Receipt += "\nadultPrice: " + adultTotal;
		Receipt +=  "\nchildTotal: " + total;
		
		return Receipt;
	}

}
