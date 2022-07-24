# Using-Interface-ploymorphism-Discount-Project-
package com.company;

import java.util.Scanner;

interface Discount {
    int getDiscount();
}

//Clothes
abstract class Clothes implements Discount {
    private String name;

    public Clothes(String name) {
        this.name = name;
    }

    public abstract int getBasePrice();

    abstract public int getDiscountPrice();

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public int getDiscount() {
        return getBasePrice() - getDiscountPrice();
    }

    public String toString() {
        return name;
    }
}

//Jacket (Winter Dress)
class Jacket extends Clothes {
    public Jacket(String name) {
        super(name);
    }

    @Override
    public int getBasePrice() {
        return 250000;
    }

    @Override
    public int getDiscountPrice() {
        return 125000;
    }

    public String toString() {
        return super.toString();
    }
}

//Shirt (Summer ِDress)
class Shirt extends Clothes {
    public Shirt(String name) {
        super(name);
    }

    @Override
    public int getBasePrice() {
        return 150000;
    }

    @Override
    public int getDiscountPrice() {
        return 60000;
    }

    public String toString() {
        return super.toString();
    }
}

//Pants 30%
class Pants extends Clothes {
    public Pants(String name) {
        super(name);
    }

    @Override
    public int getBasePrice() {
        return 80000;
    }

    @Override
    public int getDiscountPrice() {
        return 24000;
    }

    public String toString() {
        return super.toString();
    }
}

//Socks
class Socks extends Clothes {
    public Socks(String name) {
        super(name);
    }

    @Override
    public int getBasePrice() {
        return 50000;
    }

    @Override
    public int getDiscountPrice() {
        return 5000;
    }

    public String toString() {
        return super.toString();
    }
}


public class main1 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        while (true) {
            System.out.println("Which Do you Want?:" +
                    "\n1) Jacket" +
                    "\n2) Socks" +
                    "\n3) Pants" +
                    "\n4) Shirt");
            System.out.println("Please Enter a Number:");
            int str = scanner.nextInt();
            switch (str) {
                case 1 -> {
                    Jacket jacket = new Jacket("Jacket");
                    System.out.println("jacket 50% OFF:" + jacket.getBasePrice() + " - " + jacket.getDiscountPrice() + " = " + jacket.getDiscount());
                }
                case 2 -> {
                    Socks socks = new Socks("Socks");
                    System.out.println("Socks 10% OFF:" + socks.getBasePrice() + " - " + socks.getDiscountPrice() + " = " + socks.getDiscount());
                }
                case 3 -> {
                    Pants pants = new Pants("Pants");
                    System.out.println("Pants 30% OFF:" + pants.getName() + " " + pants.getBasePrice() + " - " + pants.getDiscountPrice() + " = " + pants.getDiscount());
                }
                case 4 -> {
                    Shirt shirt = new Shirt("Shirt");
                    System.out.println("Shirt 40% OFF:" + shirt.getBasePrice() + " - " + shirt.getDiscountPrice() + " = " + shirt.getDiscount());
                }
                default -> System.out.println("PLease enter valid Number...!!!");
            }
        }
    }
}
