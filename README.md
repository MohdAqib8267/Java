# Java
**Static Variable:** A static variable in Java is a variable that's associated with a class, rather than with any specific instance of the class. This means that there is only one copy of the variable in memory, even if there are multiple instances of the class.

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
	
}

public class Demo {
	public static void main(String[] args) 
	{
		Mobile obj1=new Mobile();
		obj1.brand="Apple";
		obj1.price=1500;
		//obj1.name="SmartPhone";
		Mobile.name="Phone";
		
		Mobile obj2=new Mobile();
		obj2.brand="Samsung";
		obj2.price=1700;
		//obj2.name="SmartPhone";
		Mobile.name="SmartPhone";
		
		//obj1.name="Phone";
		Mobile.name="SmartPhone";
		
		obj1.show(); //op:  Apple:1500:smartPhone // because point to same (static) variable, that is only one copy for all
		obj2.show(); //op:  Samsung:1700:smartPhone
		
		//System.out.println(obj1.brand);

	
	}
}

```

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
**Static Block:**When a block is associated with the word **static**, it is called a static block. A static block can be used for the static initialization of a class. The code that is written inside the static block run once, when the class is getting loaded into the memory.

// 1st class is loaded then object inisiated

```
class Mobile{
	String brand;
	int price;
	String network;
	static String name;
	static{
		name="Phone";
		System.out.println("in static block");
	}
	Mobile(){
		brand="";
		price=200;
//		name="Phone"; // insted of here, define name in static, then it will not initialize again and again whenever object is created.
		System.out.println("in constructor");
	}
	public void show() {
		System.out.println(brand+" : "+price+" : "+name);
	}
}
public class Demo {
	public static void main(String[] args) throws ClassNotFoundException
	{
		
		Class.forName("Mobile"); // using this we can loaded class without creation of object.
		
//		Mobile obj1=new Mobile();
//		obj1.brand="Apple";
//		obj1.price=1500;
//		Mobile.name="SmartPhone";
//		
//		Mobile obj2=new Mobile();

	
	}
}

```
**Collection API**:
Collection API -> concept //
Collection -> Interface //
Collections -> classe with multiple methods//
			    different type of data structures//
