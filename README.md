# CS305 Project Two: Practices for Secure Software

## Client Overview
Our client for this project was **Artemis Financial**, a company that develops financial applications. The client requested an assessment and enhancement of their software security. Specifically, they wanted to address vulnerabilities in their application to ensure data confidentiality, integrity, and secure communication between clients and servers.

## Project Summary
In this project, I performed a comprehensive vulnerability assessment of Artemis Financial’s application. I identified security weaknesses, implemented mitigation strategies, and refactored code to enhance overall security. Using **SHA-256** hashing, I strengthened data protection and ensured secure transmission of sensitive information.

## Key Accomplishments
- Conducted a thorough review of the application to find security vulnerabilities.
- Applied secure coding practices to prevent potential exploits.
- Added layers of security to protect client data and improve software integrity.

## Challenges and Learning Points
One of the most challenging parts of the vulnerability assessment was identifying all potential entry points for security threats. However, it was also the most helpful, as it allowed me to systematically strengthen weak areas.

To increase layers of security, I implemented **SHA-256 hashing**, ensured secure communication protocols, and refactored vulnerable code. In the future, I would use tools such as **Dependency-Check** and static code analysis to assess vulnerabilities and determine the best mitigation strategies.

## Verification and Testing
After refactoring the code, I verified that the software remained functional and secure by testing critical features and ensuring no new vulnerabilities were introduced. This included verifying encrypted data transmission and validating hashed outputs.

## Tools and Practices Used
- **SHA-256 hashing** for secure data handling
- Secure coding standards
- Manual code review and testing
- Documentation of mitigation strategies for reproducibility

## Professional Application
This assignment demonstrates practical skills in identifying vulnerabilities, applying secure coding practices, and implementing cryptographic techniques. Future employers could see this project as evidence of my ability to enhance software security while maintaining functionality and reliability.

## Example: SHA-256 Hashing in Java
```java
import java.security.MessageDigest;
import java.security.NoSuchAlgorithmException;

public class SHA256Example {
    public static void main(String[] args) {
        try {
            String data = "SensitiveInformation";
            MessageDigest digest = MessageDigest.getInstance("SHA-256");
            byte[] hash = digest.digest(data.getBytes("UTF-8"));

            // Convert bytes to hexadecimal
            StringBuilder hexString = new StringBuilder();
            for (byte b : hash) {
                String hex = Integer.toHexString(0xff & b);
                if(hex.length() == 1) hexString.append('0');
                hexString.append(hex);
            }

            System.out.println("SHA-256 Hash: " + hexString.toString());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
