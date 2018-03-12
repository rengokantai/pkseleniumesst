# pkseleniumesst
## 4. Selenium WebDriver Best Practices
method1
```
if(isElementPresent())
```
method2
```
if(driver.findElements().size()>0)
```

### Waits
#### Explicit wait
```
public class classname{
  private WebDriver driver;
  private final Wait<WebDriver> wait;
  
  public classname(WebDriver driver) {
    this.driver=driver;
    wait=new WebDriverWait(dirver,10);
  }
}
```

#### The FluentWait method
```
FluentWait<WebDriver> wait = new FluentWait<WebDriver>(driver).withTimeout(10,TimeUnit.SECONDS).pollingEvery(2,TimeUnit.SECONDS).ignoring
(NoSuchElementException.class);

WebElement doo =wait.until(new Function<WebDriver,WebElement>(){
  public WebElement apply(WebDriver driver){
    return driver.findElement(locator);
  }
});
```
