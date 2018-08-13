# SeleniumTestAutomationOnChrome
Web Application Test Script using Selenium WebDriver &amp; Java on Chrome in Incognito Mode

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.remote.DesiredCapabilities;

public class ChromePrivateBrowsing {

    public static void main(String args[]){
        createChromeInstance();
    }

    public static WebDriver createChromeInstance(){
        DesiredCapabilities capabilities = DesiredCapabilities.chrome();
        ChromeOptions options = new ChromeOptions();
        options.addArguments("--incognito");
        capabilities.setCapability(ChromeOptions.CAPABILITY, options);
        System.setProperty("webdriver.chrome.driver","C:\\chromedriver.exe");
        WebDriver driver = new ChromeDriver(capabilities);
        driver.get("http://www.google.com");
        return driver;
    }
}
