# Lab-8 
# Lab Excercises

1. Create a new Eclipse project, and within the project create a package and also 
2. Create a class for a Boa.


![image](https://user-images.githubusercontent.com/123457236/233316325-4e0d729e-5ece-4852-a810-e0bc212ae3a7.png)

3. Now a test case is needed to be created for the class Boa.

```
import org.junit.Assert;
import org.junit.Test;
public class boatest 
{
  @Test
  public void testIsHealthy() 
  {
    boa healthyBoa = new boa("Lucy", 8, "granola bars");
    Assert.assertTrue(healthyBoa.isHealthy());
    
    boa sickBoa = new boa("Sneaky", 6, "mice");
    Assert.assertFalse(sickBoa.isHealthy());
  }

  @Test
  public void testFitsInCage() 
  {
    boa smallBoa = new boa("Tiny", 2, "rats");
    Assert.assertTrue(smallBoa.fitsInCage(5));
    Assert.assertFalse(smallBoa.fitsInCage(1));

    boa largeBoa = new boa("Goliath", 20, "chicken");
    Assert.assertTrue(largeBoa.fitsInCage(25));
    Assert.assertFalse(largeBoa.fitsInCage(10));
  }
}
```

![image](https://user-images.githubusercontent.com/123457236/233330142-952d4591-14b1-4167-8ec4-3d3535ae1bae.png)


4. Modifying testIsHealthy method in boa class:

```
@Test
public void testIsHealthy() {
    // check that jen is not healthy
    assertFalse(jen.isHealthy());
    
    // check that ken is healthy
    assertTrue(ken.isHealthy());
}
```

5. modifying testFitsInCage() method in the boatest class :

```
@Test
public void testFitsInCage() {
    // Test for jen
    assertFalse(jen.fitsInCage(1)); // cage length is less than length of boa
    assertTrue(jen.fitsInCage(2)); // cage length is equal to length of boa
    assertTrue(jen.fitsInCage(3)); // cage length is greater than length of boa

    // Test for ken
    assertFalse(ken.fitsInCage(2)); // cage length is less than length of boa
    assertTrue(ken.fitsInCage(3)); // cage length is equal to length of boa
    assertTrue(ken.fitsInCage(4)); // cage length is greater than length of boa
}
```

6. Running Test Cases:

![image](https://user-images.githubusercontent.com/123457236/233331777-39d97ab8-36a6-4384-9e8e-537b12508eca.png)

7. Here's the modified Boa class with the new lengthInInches() method:

```
public class Boa {
    private String name;
    private int length; // the length of the boa, in feet
    private String favoriteFood;

    public Boa(String name, int length, String favoriteFood) {
        this.name = name;
        this.length = length;
        this.favoriteFood = favoriteFood;
    }

    // returns true if this boa constrictor is healthy
    public boolean isHealthy() {
        return this.favoriteFood.equals("granola bars");
    }

    // returns true if the length of this boa constrictor is
    // less than the given cage length
    public boolean fitsInCage(int cageLength) {
        return this.length < cageLength;
    }

    // produces the length of the Boa in inches
    public int lengthInInches() {
        return this.length * 12;
    }
}
```

The example of a new test case in the BoaTest class that tests the lengthInInches() method:

```
import static org.junit.Assert.assertEquals;
import org.junit.Before;
import org.junit.Test;

public class BoaTest {
    private Boa jen;
    private Boa ken;

    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }

    @Test
    public void testLengthInInches() {
        assertEquals(24, jen.lengthInInches());
        assertEquals(36, ken.lengthInInches());
    }
}
```

- Here The @Test annotation indicates that this is a test method that should be run by JUnit.
- This new test case checks whether  the lengthInInches() method returns the expected value when called by each of the Boa objects created in the setUp() method. 
- It uses the assertEquals() method to compare the expected value to the actual value returned by the lengthInInches() method. 






