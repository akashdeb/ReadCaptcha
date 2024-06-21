# ReadCaptcha

In order handle Captcha you need to download the eng.traineddata file from this repository and in your C driver create a tessdata folder and add the file init.
Furthermore show the path of the tessdata folder in your System varaible in Environment Variabled of your Windows System.

![image](https://user-images.githubusercontent.com/62165769/234275320-9452fb39-4165-43c8-9f16-38f0c503f19d.png)

eng.traineddata file you need to also add it to project in ./eng.traineddata location.

You need add the Tess4J Tesseract For Java depedency to your maven project:

<!-- https://mvnrepository.com/artifact/net.sourceforge.tess4j/tess4j -->
<dependency>
    <groupId>net.sourceforge.tess4j</groupId>
    <artifactId>tess4j</artifactId>
    <version>4.5.4</version>
</dependency>

You need to take the screen shot of the captcha:

Files.copy(driver.findElement(By.tagName("canvas")).getScreenshotAs(OutputType.FILE), new File("./captchaImage.png"));	

Use the following snippet to capture the characters from the screenshot:
String captcha = new Tesseract().doOCR(new File("./captchaImage.png"));

Note: The captured Captcha will not always correct.

Happy Testing!
