# Lab-8_202001011
## Software Engineering
```
    Name: Vansh Parikh
    Student ID: 202001011
    Lab: 8 (Software Engineering)
```

### (1) Create a new Eclipse project, and within the project create a package.

![image](https://user-images.githubusercontent.com/124344810/233607140-5529e924-fc13-4331-8504-9df5708fe4fb.png)

### (2) Create a class for a Boa :

```
package src;

public class Boa {
	private String name;
	private int length; // the length of the boa, in feet
	private String favoriteFood;
	public Boa (String name, int length, String favoriteFood){
	this.name = name;
	this.length = length;
	this.favoriteFood = favoriteFood;
	}
	// returns true if this boa constrictor is healthy
	public boolean isHealthy(){
	return this.favoriteFood.equals("granola bars");
	}
	// returns true if the length of this boa constrictor is
	// less than the given cage length
	public boolean fitsInCage(int cageLength){
	return this.length < cageLength;
	}
}

```

### (4) Modified setUp() method in the BoaTest class :

```
@Before
	public void setUp() throws Exception {
	jen = new Boa("Jennifer", 2, "grapes");
	ken = new Boa ("Kenneth", 3, "granola bars");
	vansh =new Boa("vansh" , 5, "mango");
	tyson = new Boa("tyson", 8, "granola bars");
	}
```

### (5.1) Modified testIsHealthy() method in the BoaTest class :

```
@Test
	public void testisHealthy() {
		assertTrue(ken.isHealthy());
		assertFalse(jen.isHealthy());
		assertFalse(vansh.isHealthy());
		assertTrue(tyson.isHealthy());
		
	}
```

### (5.2) Modified testFitsInCage() method in the BoaTest class :
```
@Test
	public void testfitsInCage() {
		assertTrue(jen.fitsInCage(5));
		assertFalse(jen.fitsInCage(2));
		assertFalse(jen.fitsInCage(1));
		
		assertFalse(ken.fitsInCage(1));
		assertFalse(ken.fitsInCage(3));
		assertTrue(ken.fitsInCage(5));
		
		assertTrue(vansh.fitsInCage(10));
		assertFalse(vansh.fitsInCage(5));
		assertFalse(vansh.fitsInCage(1));
		
		assertFalse(tyson.fitsInCage(7));
		assertFalse(tyson.fitsInCage(8));
		assertTrue(tyson.fitsInCage(15));
	}
```


### (6) Running Testcases

![image](https://user-images.githubusercontent.com/124344810/233608460-63a9c90b-92e5-4fa2-8e53-fdc7cdbdcf41.png)


### (7)The updated Boa class with the new lengthInInches() method is shown below:

```
package src;

public class Boa {
	private String name;
	private int length; // the length of the boa, in feet
	private String favoriteFood;
	public Boa (String name, int length, String favoriteFood){
	this.name = name;
	this.length = length;
	this.favoriteFood = favoriteFood;
	}
	// returns true if this boa constrictor is healthy
	public boolean isHealthy(){
	return this.favoriteFood.equals("granola bars");
	}
	// returns true if the length of this boa constrictor is
	// less than the given cage length
	public boolean fitsInCage(int cageLength){
	return this.length < cageLength;
	}

	public int lengthInInches(){
		return this.length*12;
	}
}
```

#### Here is an illustration of a fresh test case for the lengthInInches() method in the BoaTest class:
```
@Test
	public void testlengthInInches() {
		int expectedlength1=24;
		int expectedlength2=36;
		int expectedlength3=60;
		int expectedlength4=96;
		
		int ansfromfunction1=jen.lengthInInches();
		int ansfromfunction2=ken.lengthInInches();
		int ansfromfunction3=vansh.lengthInInches();
		int ansfromfunction4=tyson.lengthInInches();
		
		assertEquals(expectedlength1,ansfromfunction1);
		assertEquals(expectedlength2,ansfromfunction2);
		assertEquals(expectedlength3,ansfromfunction3);
		assertEquals(expectedlength4,ansfromfunction4);
	}
```

This new test case verifies that each of the Boa objects created in the setUp() function returns the expected value when the lengthInInches() method is called on it. The expected number and the actual value returned by the lengthInInches() method are compared using the assertEquals() method. This test function should be executed by JUnit, according to the @Test annotation.

#### Running all the test-cases (including testlengthInInches)

![image](https://user-images.githubusercontent.com/124344810/233608961-28b0f831-0a81-4379-adb3-a7d830def777.png)



