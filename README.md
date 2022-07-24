# Using-Interface-ploymorphism-Discount-Project-
package com.company;

import java.util.Scanner;

interface Discount {
    public int getDiscount();
}

//Clothes
abstract class Clothes implements Discount {
    protected String name;
    protected int basePrice;
    protected int discountPrice;


    protected Clothes(String name) {
        this.name = name;

    }

    public int getBasePrice() {
        return basePrice;
    }

    public void setBasePrice(int basePrice) {
        this.basePrice = basePrice;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getDiscountPrice() {
        return discountPrice;
    }

    public void setDiscountPrice(int discountPrice) {
        this.discountPrice = discountPrice;
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
    protected String name;

    protected Jacket(String name) {
        super(name);
        this.name = name;
    }

    @Override
    public int getBasePrice() {
        return 250000;
    }

    @Override
    public String getName() {
        return name;
    }

    @Override
    public void setName(String name) {
        this.name = name;
    }

    @Override
    public int getDiscountPrice() {
        return 125000;
    }


    public String toString() {
        return name;
    }
}

//Shirt (Summer ِDress)
class Shirt extends Clothes {
    protected String name;

    public Shirt(String name) {
        super(name);
        this.name = name;
    }

    @Override
    public int getBasePrice() {
        return 150000;
    }

    @Override
    public String getName() {
        return name;
    }

    @Override
    public void setName(String name) {
        this.name = name;
    }


    @Override
    public int getDiscountPrice() {
        return 60000;
    }


    public String toString() {
        return name;
    }
}

//Pants 30%
class Pants extends Clothes {
    protected String name;

    public Pants(String name) {
        super(name);
        this.name = name;
    }

    @Override
    public int getBasePrice() {
        return 80000;
    }

    @Override
    public String getName() {
        return name;
    }

    @Override
    public void setName(String name) {
        this.name = name;
    }

    @Override
    public int getDiscountPrice() {
        return 24000;
    }


    public String toString() {
        return name;
    }
}

//Socks
class Socks extends Clothes {
    protected String name;

    public Socks(String name) {
        super(name);
        this.name = name;
    }

    @Override
    public String getName() {
        return name;
    }

    @Override
    public void setName(String name) {
        this.name = name;
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
        return name;
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
                    System.out.println("Pants 30% OFF:" + pants.getBasePrice() + " - " + pants.getDiscountPrice() + " = " + pants.getDiscount());
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
