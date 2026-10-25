##Artemis Financial


### 1. Client Summary and Software Requirements

* **The Client:** Artemis Financial is a financial services firm that handles sensitive customer data and financial transactions, making information protection and secure communications critical requirements.


* **Company Issues & Requirements:** The company needed to address external threats such as unauthorized access, malicious inputs, information leaks, and vulnerable application components. Key requirements included protecting data during transmission (via encryption), safely managing international transactions, modernizing the application's open-source dependencies, and securing API endpoints.



### 2. Vulnerability Discovery, Secure Coding, and Business Value

* **What Was Done Well:** Conducted a rigorous manual source code review alongside a comprehensive static analysis scan using OWASP Dependency-Check version 12.1.9, successfully uncovering 252 vulnerabilities across 11 vulnerable third-party dependencies as well as critical code-level security weaknesses.


* **Importance of Secure Coding & Business Value:** Secure coding is crucial to protect sensitive user data from exploitation, data breaches, and unauthorized tampering. Proactive software security safeguards a company's overall well-being by maintaining customer trust, ensuring regulatory compliance, preventing costly financial and operational disruptions, and protecting brand reputation.



### 3. Challenging and Helpful Aspects of the Assessment

* **Insights:** Utilizing static analysis tools like OWASP Dependency-Check was immensely helpful in systematically uncovering deep-seated transitive vulnerabilities (such as critical issues in Spring Boot, Tomcat, and SnakeYAML) that manual inspection alone might miss. Examining specific CVEs—such as CVE-2026-54512 (Jackson Databind polymorphic deserialization) and CVE-2025-35036 (Hibernate Validator expression language injection)—provided practical clarity on how third-party component flaws can compromise an application.



### 4. Increasing Layers of Security and Future Assessment Methods

* **Layers of Security:** Defense-in-depth was established by updating vulnerable third-party dependencies, removing hardcoded database credentials in favor of secure configuration management, replacing the high-privileged root database account with a dedicated restricted account, introducing input validation, adding authentication and authorization controls to sensitive endpoints (such as `/read`), and replacing raw stack trace logging with controlled error handling.


* **Future Assessment Approach:** Moving forward, vulnerability assessments will rely on automated static analysis tools (like OWASP Dependency-Check), dynamic testing, and NVD/CVE advisory reviews to prioritize mitigations based on CVSS severity scores and active exploitability.



### 5. Ensuring Functionality and Preventing New Vulnerabilities

* **Ensuring Functionality and Security:** Code functionality was maintained while refactoring by applying secure coding standards, adhering to resource management best practices (such as proper database connection closure), and validating input parameters.


* **Post-Refactoring Verification:** To ensure refactoring did not introduce new vulnerabilities, automated dependency scans and code reviews were re-executed to verify that all flagged issues and outdated libraries were successfully remediated.



### 6. Helpful Resources, Tools, and Coding Practices

* **Tools and Resources:** OWASP Dependency-Check, the National Vulnerability Database (NVD), vendor security advisories, and CVE documentation.


* **Coding Practices:** Principle of least privilege (using dedicated database accounts instead of root), secure resource management (try-with-resources), controlled exception logging (avoiding `printStackTrace()`), input validation, and regular dependency maintenance.



### 7. Value for Future Employers

* **Portfolio Showcase:** This artifact demonstrates practical proficiency in performing static application security testing (SAST), analyzing CVE reports, conducting manual code reviews, formulating actionable mitigation plans, and implementing secure software development life cycle (SDLC) practices tailored to enterprise financial environments.
