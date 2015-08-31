==Security Test Data Analysis and Reporting==
'''Goals for Security Test Metrics and Measurements'''<br>
Defining the goals for the security testing metrics and measurements is a prerequisite for using security testing data for risk analysis and management processes. For example, a measurement such as the total number of vulnerabilities found with security tests might quantify the security posture of the application. These measurements also help to identify security objectives for software security testing. For example, reducing the number of vulnerabilities to an acceptable number (minimum) before the application is deployed into production. 

Another manageable goal could be to compare the application security posture against a baseline to assess improvements in application security processes. For example, the security metrics baseline might consist of an application that was tested only with penetration tests. The security data obtained from an application that was also security tested during coding should show an improvement (e.g., fewer number of vulnerabilities) when compared with the baseline.

In traditional software testing, the number of software defects, such as the bugs found in an application, could provide a measure of software quality. Similarly, security testing can provide a measure of software security. From the defect management and reporting perspective, software quality and security testing can use similar categorizations for root causes and defect remediation efforts. From the root cause perspective, a security defect can be due to an error in design (e.g., security flaws) or due to an error in coding (e.g., security bug). From the perspective of the effort required to fix a defect, both security and quality defects can be measured in terms of developer hours to implement the fix, the tools and resources required to fix, and the cost to implement the fix.

A characteristic of security test data, compared to quality data, is the categorization in terms of the threat, the exposure of the vulnerability, and the potential impact posed by the vulnerability to determine the risk. Testing applications for security consists of managing technical risks to make sure that the application countermeasures meet acceptable levels. For this reason, security testing data needs to support the security risk strategy at critical checkpoints during the SDLC. For example, vulnerabilities found in source code with source code analysis represent an initial measure of risk. A measure of risk (e.g., high, medium, low) for the vulnerability can be calculated by determining the exposure and likelihood factors and by validating the vulnerability with penetration tests. The risk metrics associated to vulnerabilities found with security tests empower business management to make risk management decisions, such as to decide whether risks can be accepted, mitigated, or transferred at different levels within the organization (e.g., business as well as technical risks).

When evaluating the security posture of an application it is important to take into consideration certain factors, such as the size of the application being developed. Application size has been statistically proven to be related to the number of issues found in the application during testing. One measure of application size is the number of lines of code (LOC) of the application. Typically,  software quality defects range from about 7 to 10 defects per thousand lines of new and changed code [21]. Since testing can reduce the overall number by about 25% with one test alone, it is logical for larger size applications to be tested more often than smaller size applications.

When security testing is done in several phases of the SDLC, the test data can prove the capability of the security tests in detecting vulnerabilities as soon as they are introduced. The test data can also prove the effectiveness of removing the vulnerabilities by implementing countermeasures at different checkpoints of the SDLC. A measurement of this type is also defined as “containment metrics” and provides a measure of the ability of a security assessment performed at each phase of the development process to maintain security within each phase. These containment metrics are also a critical factor in lowering the cost of fixing the vulnerabilities. It is less expensive to deal with vulnerabilities in the same phase of the SDLC that they are found, rather then fixing them later in another phase. 

Security test metrics can support security risk, cost, and defect management analysis when they are associated with tangible and timed goals such as: 
*Reducing the overall number of vulnerabilities by 30%
*Fixing security issues by a certain deadline (e.g., before beta release) 

Security test data can be absolute, such as the number of vulnerabilities detected during manual code review, as well as comparative, such as the number of vulnerabilities detected in code reviews compared to penetration tests. To answer questions about the quality of the security process, it is important to determine a baseline for what could be considered acceptable and good. 

Security test data can also support specific objectives of the security analysis. These objects could be compliance with security regulations and information security standards, management of security processes, the identification of security root causes and process improvements, and security cost benefit analysis.

When security test data is reported it has to provide metrics to support the analysis. The scope of the analysis is the interpretation of test data to find clues about the security of the software being produced as well the effectiveness of the process. 

Some examples of clues supported by security test data can be:
*Are vulnerabilities reduced to an acceptable level for release?
*How does the security quality of this product compare with similar software products?
*Are all security test requirements being met? 
*What are the major root causes of security issues?
*How numerous are security flaws compared to security bugs?
*Which security activity is most effective in finding vulnerabilities?
*Which team is more productive in fixing security defects and vulnerabilities?
*Which percentage of overall vulnerabilities are high risk?
*Which tools are most effective in detecting security vulnerabilities?
*Which kind of security tests are most effective in finding vulnerabilities (e.g., white box vs. black box) tests?
*How many security issues are found during secure code reviews?
*How many security issues are found during secure design reviews?

In order to make a sound judgment using the testing data, it is important to have a good understanding of the testing process as well as the testing tools. A tool taxonomy should be adopted to decide which security tools to use. Security tools can be qualified as being good at finding common known vulnerabilities targeting different artifacts.

The issue is that the unknown security issues are not tested. The fact that a security test is clear of issues does not mean that the software or application is good. Some studies [22] have demonstrated that, at best, tools can only find 45% of overall vulnerabilities. 

Even the most sophisticated automation tools are not a match for an experienced security tester. Just relying on successful test results from automation tools will give security practitioners a false sense of security.  Typically, the more experienced the security testers are with the security testing methodology and testing tools, the better the results of the security test and analysis will be. It is important that managers making an investment in security testing tools also consider an investment in hiring skilled human resources as well as security test training.

'''Reporting Requirements'''<br>
The security posture of an application can be characterized from the perspective of the effect, such as number of vulnerabilities and the risk rating of the vulnerabilities, as well as from the perspective of the cause or origin, such as coding errors, architectural flaws, and configuration issues.  

Vulnerabilities can be classified according to different criteria. The most commonly used vulnerability severity metric is the Forum of Incident Response and Security Teams (FIRST) Common Vulnerability Scoring System (CVSS), which is currently in release version 2 with version 3 due for release shortly.

When reporting security test data the best practice is to include the following information:
*The categorization of each vulnerability by type
*The security threat that the issue is exposed to
*The root cause of security issues (e.g., security bugs, security flaw)
*The testing technique used to find the issue
*The remediation of the vulnerability (e.g., the countermeasure) 
*The severity rating of the vulnerability (High, Medium, Low and/or CVSS score)

By describing what the security threat is, it will be possible to understand if and why the mitigation control is ineffective in mitigating the threat. 

Reporting the root cause of the issue can help pinpoint what needs to be fixed. In the case of a white box testing, for example, the software security root cause of the vulnerability will be the offending source code. 

Once issues are reported, it is also important to provide guidance to the software developer on how to re-test and find the vulnerability. This might involve using a white box testing technique (e.g., security code review with a static code analyzer) to find if the code is vulnerable. If a vulnerability can be found via a black box technique (penetration test), the test report also needs to provide information on how to validate the exposure of the vulnerability to the front end (e.g., client).

The information about how to fix the vulnerability should be detailed enough for a developer to implement a fix. It should provide secure coding examples, configuration changes, and provide adequate references.

Finally, the severity rating contributes to the calculation of risk rating and helps to prioritize the remediation effort. Typically, assigning a risk rating to the vulnerability involves external risk analysis based upon factors such as impact and exposure.

'''Business Cases'''<br> 
For the security test metrics to be useful, they need to provide value back to the organization's security test data stakeholders. The stakeholders can include project managers, developers, information security offices, auditors, and chief information officers. The value can be in terms of the business case that each project stakeholder has in terms of role and responsibility.

Software developers look at security test data to show that software is coded more securely and efficiently. This allows them to make the case for using source code analysis tools as well as following secure coding standards and attending software security training. 

Project managers look for data that allows them to successfully manage and utilize security testing activities and resources according to the project plan. To project managers, security test data can show that projects are on schedule and moving on target for delivery dates and are getting better during tests. 

Security test data also helps the business case for security testing if the initiative comes from information security officers (ISOs). For example, it can provide evidence that security testing during the SDLC does not impact the project delivery, but rather reduces the overall workload needed to address vulnerabilities later in production. 

To compliance auditors, security test metrics provide a level of software security assurance and confidence that security standard compliance is addressed through the security review processes within the organization. 

Finally, Chief Information Officers (CIOs) and Chief Information Security Officers (CISOs), who are responsible for the budget that needs to be allocated in security resources, look for derivation of a cost benefit analysis from security test data. This allows them to make informed decisions on which security activities and tools to invest. One of the metrics that supports such analysis is the Return On Investment (ROI) in Security [23]. To derive such metrics from security test data, it is important to quantify the differential between the risk due to the exposure of vulnerabilities and the effectiveness of the security tests in mitigating the security risk, and factor this gap with the cost of the security testing activity or the testing tools adopted.
