// # Selenium-Script

package AutomationQa.MVTproj;
import java.time.Duration;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;
import io.github.bonigarcia.wdm.WebDriverManager;

public class Demo {

	@Test
	public void sampleAutomation() throws InterruptedException {
		WebDriverManager.chromedriver().setup();
		WebDriver driver = new ChromeDriver();

		// Step 1: Open the e-commerce website
		driver.get("https://tutorialsninja.com/demo/");
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5));

		// Step 2: Log in to the account
		driver.findElement(By.xpath("//a[@title= \"My Account\"]")).click();
		driver.findElement(By.linkText("Login")).click();
		
		driver.findElement(By.id("input-email")).sendKeys("vineetshukla14u@gmail.com");
		
		driver.findElement(By.id("input-password")).sendKeys("Selenium@123");
		
		driver.findElement(By.xpath("//input[@type=\"submit\"]")).click();

		// Step 3: Search for "iPhone"
		WebElement searchBox = driver.findElement(By.name("search"));
		searchBox.sendKeys("iPhone");
		driver.findElement(By.xpath("//button[@class= \"btn btn-default btn-lg\"]")).click();
	

		// Step 4: Select the desired product from search results
		driver.findElement(By.linkText("iPhone")).click();
		

		// Step 5: Add the product to the cart
		driver.findElement(By.id("button-cart")).click();
	

		// Step 6: Go to the shopping cart
		driver.findElement(By.id("cart-total")).click();
		

		// Step 7: Proceed to checkout
		driver.findElement(By.linkText("Checkout")).click();
		

		driver.quit();
	}

}

