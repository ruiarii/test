# test
package guru99Application;

import static org.testng.Assert.assertEquals;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;

public class Guru99ApplicationTest {
	
	ChromeDriver driver;
	String url ="https://demo.guru99.com/v4/";
	@BeforeMethod
	public void invokeBrowser() {
		
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\Administrator\\Desktop\\Selenium Testing\\chromedriver.exe");
		driver = new ChromeDriver();
		
		driver.manage().window().maximize();
		driver.get(url);
	}
	
	
	@Test(priority = 0)
	public void verifyTitleOfThePage() {
		
		String expectedTitle = "Guru99 Bank Home Page";
		
		String actualTitle= driver.getTitle();
		
		Assert.assertEquals(actualTitle, expectedTitle);
	}
	
	@Test(priority = 100)
	public void verifyLoginToGuru99Application() {
		
		WebElement userId = driver.findElement(By.name("uid"));
		
		WebElement userPassword = driver.findElement(By.name("password"));
		
		WebElement loginButton = driver.findElement(By.name("btnLogin"));
		
		userId.sendKeys("mngr558703");
		
		userPassword.sendKeys("nEdegAr");
		
		loginButton.click();
		
		
	}
	@Test
	public void addCustomer() {
		
		WebElement addCustomerLink = driver.findElement(By.linkText("New Customer"));
		
		addCustomerLink.click();
		
		driver.findElement(By.xpath("//input [@value='f']")).click();
		
		driver.findElement(By.name("name")).sendKeys("Adam");
		
		driver.findElement(By.name("dob")).sendKeys("06/06/1989");
		
		driver.findElement(By.name("addr")).sendKeys("Tunis");
		
		driver.findElement(By.name("city")).sendKeys("ariana");
		
		driver.findElement(By.name("state")).sendKeys("Tunis");
		
		driver.findElement(By.name("pinno")).sendKeys("122001");
		
		driver.findElement(By.name("telephoneno")).sendKeys("97432567");
		
		driver.findElement(By.name("emailid")).sendKeys("abc@xyz");
		
		
		driver.findElement(By.name("password")).sendKeys("123");
		
		driver.findElement(By.name("sub")).click();
		
	}

}
