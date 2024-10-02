# Java

**Static Method:** A static method in Java is a method that is part of a class rather than an instance of that class. Every instance of a class(objects) has access to the instance method.
Static methods have access to class variables (static variables) without using the class's object (instance). Only static data may be accessed by a static method.

```
class Mobile{
	String brand;
	int price;
	String network;
//	String name;
	static String name;
	
	public void show() {
		System.out.println(brand+" : "+price+" : "+name);
	}
	
	public static void show1(Mobile obj)
	{
//		System.out.println("in static method");
		System.out.println(obj.brand+" : "+ obj.price +" : "+obj.name);
    // System.out.println(obj.brand+" : "+ obj.price +" : "+name); // direcg name b call kr skte h because name is static, and we can use static variable in static method directly
	}
}

public class Demo {
	public static void main(String[] args) 
	{
		Mobile obj1=new Mobile();
		obj1.brand="Apple";
		obj1.price=1500;
		//obj1.name="SmartPhone";
		Mobile.name="SmartPhone"; // because it is associated with class not object
		
		Mobile obj2=new Mobile();
		obj2.brand="Samsung";
		obj2.price=1700;
		//obj2.name="SmartPhone";
		Mobile.name="SmartPhone";
		
		//obj1.name="Phone";
		Mobile.name="SmartPhone";
		
		obj1.show(); //Op: Apple:1500:smartPhone
		obj2.show(); //op: samsung:1700:smartPhone 
		
		Mobile.show1(obj1);  //op: Apple:1500:smartPhone
		
		//System.out.println(obj1.brand);
	
	}
}
```
