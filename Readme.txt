Process:
1. Create a folder that contains the src directory and the pom.xml file.
2. Write project information in the pom.xml file and add Spring Boot dependencies.
3. Create the /main/java/com.example.exam package in the src directory,and then create the Spring Boot startup class ExamApplication and controller package under the com.example.exam package.
4. Create the ApiController class in the controller package, and then implement the Inch to Centimeter and Yard to Meter methods in it. Remember to add annotations such as @Controller, @RequestMapping, @GetMapping.
5. Finally, run mvn spring-boot:run in the root directory of the project to start the application.

Requirement definitions:
As a Imperial converter, I want to receive imperial values like inch or yard, so that convert them to metric ones like centimeter or meter.

Implementation:
Inch to Centimeter:
    @GetMapping(value = "/centimeter")
    @ResponseBody
    public String I2C(String inch) {
        if (inch == null) {
            return "";
        }
        try {
            double centimeter = Double.valueOf(inch) * 2.54;
            return String.valueOf(centimeter);
        } catch (Exception e) {
            return "";
        }
    }

Yard to Meter:
    @GetMapping(value = "/meter")
    @ResponseBody
    public String Y2M(String yard) {
        if (yard == null) {
            return "";
        }
        try {
            double meter = Double.valueOf(yard) / 1.094;
            return String.valueOf(meter);
        } catch (Exception e) {
            return "";
        }
    }

Correct status / Linking / Branching:
The correct state is to display the correct number in the web page.
Manage with GitHub.

Testing:
1. http://localhost:8080/api/centimeter?inch=1
display 2.54
2. http://localhost:8080/api/meter?yard=1
display 0.9140767824497257

Pipeline:
This project is managed by Maven, and the project can be maintained continuously.

Artefacts:
The Project can continuous delivery.
