// # Selenium-Script

import java.time.Duration;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class Demo6 {
    public static void main(String[] args) throws InterruptedException {
        // Set up WebDriver
        System.setProperty("webdriver.chrome.driver", "C:\\Users\\Asus\\Downloads\\chromedriver-win64\\chromedriver-win64\\chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        // Step 1: Open the e-commerce website
        driver.get("https://tutorialsninja.com/demo/");
        driver.manage().window().maximize();
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(2));

        // Step 2: Log in to the account
        driver.findElement(By.xpath("//a[@title= \"My Account\"]")).click();
        driver.findElement(By.linkText("Login")).click();
        Thread.sleep(2000);
        driver.findElement(By.id("input-email")).sendKeys("vineetshukla14u@gmail.com");
        Thread.sleep(2000);
        driver.findElement(By.id("input-password")).sendKeys("Selenium@123");
        Thread.sleep(2000);
        driver.findElement(By.xpath("//input[@type=\"submit\"]")).click();
        Thread.sleep(3000);

        // Step 3: Search for "iPhone"
        WebElement searchBox = driver.findElement(By.name("search"));
        searchBox.sendKeys("iPhone");
        driver.findElement(By.xpath("//button[@class= \"btn btn-default btn-lg\"]")).click();
        Thread.sleep(3000);

        // Step 4: Select the desired product from search results
        driver.findElement(By.linkText("iPhone")).click();
        Thread.sleep(2000);

        // Step 5: Add the product to the cart
        driver.findElement(By.id("button-cart")).click();
        Thread.sleep(2000);

        // Step 6: Go to the shopping cart
        driver.findElement(By.id("cart-total")).click();
        Thread.sleep(2000);

        // Step 7: Proceed to checkout
        driver.findElement(By.linkText("Checkout")).click();
        Thread.sleep(3000);
        
        driver.quit();
    }
}


