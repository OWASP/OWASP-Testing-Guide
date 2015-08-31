==Principles of Testing==

There are some common misconceptions when developing a testing methodology to find security bugs in software. This chapter covers some of the basic principles that professionals should take into account when performing security tests on software. 

'''There is No Silver Bullet'''<br>
While it is tempting to think that a security scanner or application firewall will provide many defenses against attack or identify a multitude of problems, in reality there is no silver bullet to the problem of insecure software. Application security assessment software, while useful as a first pass to find low-hanging fruit, is generally immature and ineffective at in-depth assessments or providing adequate test coverage. Remember that security is a process and not a product. 

'''Think Strategically, Not Tactically'''<br>
Over the last few years, security professionals have come to realize the fallacy of the patch-and-penetrate model that was pervasive in information security during the 1990’s. The patch-and-penetrate model involves fixing a reported bug, but without proper investigation of the root cause. This model is usually associated with the window of vulnerability shown in the figure below. The evolution of vulnerabilities in common software used worldwide has shown the ineffectiveness of this model. For more information about the window of vulnerability please refer to [6]. 

Vulnerability studies [7] have shown that with the reaction time of attackers worldwide, the typical window of vulnerability does not provide enough time for patch installation, since the time between a vulnerability being uncovered and an automated attack against it being developed and released is decreasing every year. 

There are several incorrect assumptions in the patch-and-penetrate model. Many users believe that patches interfere with normal operations and might break existing applications. It is also incorrect to assume that all users are aware of newly released patches. Consequently not all users of a product will apply patches, either because they think patching may interfere with how the software works or because they lack knowledge about the existence of the patch.<br>


<center>[[Image:WindowExposure.jpg]]<br>
''Figure 2: Window of Vulnerability''</center><br> 

It is essential to build security into the Software Development Life Cycle (SDLC) to prevent reoccurring security problems within an application. Developers can build security into the SDLC  by developing standards, policies, and guidelines that fit and work within the development methodology. Threat modeling and other techniques should be used to help assign appropriate resources to those parts of a system that are most at risk. 
<br>

'''The SDLC is King'''<br>
The SDLC is a process that is well-known to developers. By integrating security into each phase of the SDLC, it allows for a holistic approach to application security that leverages the procedures already in place within the organization. Be aware that while the names of the various phases may change depending on the SDLC model used by an organization, each conceptual phase of the archetype SDLC will be used to develop the application (i.e., define, design, develop, deploy, maintain). Each phase has security considerations that should become part of the existing process, to ensure a cost-effective and comprehensive security program.

There are several secure SDLC frameworks that exist that provide both descriptive and prescriptive advice. Whether a person takes descriptive or prescriptive advice depends on the maturity of the SDLC process. Essentially, prescriptive advice shows how the secure SDLC should work, and descriptive advice shows how its used in the real world. Both have their place. For example, if you don't know where to start, a prescriptive framework can provide a menu of potential security controls that can be applied within the SDLC. Descriptive advice can then help drive the decision process by presenting what has worked well for other organizations. Descriptive secure SDLCs include BSIMM-V; and the prescriptive secure SDLCs inculde OWASP's Open Software Assurance Maturity Model (OpenSAMM) and ISO/IEC 27034 Parts 1-8, parts of which are still in development. 
<br>
'''Test Early and Test Often'''<br>
When a bug is detected early within the SDLC it can be addressed faster and at a lower cost. A security bug is no different from a functional or performance-based bug in this regard. A key step in making this possible is to educate the development and QA teams about common security issues and the ways to detect and prevent them. Although new libraries, tools, or languages can help design better programs (with fewer security bugs), new threats arise constantly and developers must be aware of the threats that affect the software they are developing. Education in security testing also helps developers acquire the appropriate mindset to test an application from an attacker's perspective. This allows each organization to consider security issues as part of their existing responsibilities.
<br>
'''Understand the Scope of Security'''<br>
It is important to know how much security a given project will require. The information and assets that are to be protected should be given a classification that states how they are to be handled (e.g., confidential, secret, top secret). Discussions should occur with legal council to ensure that any specific security requirements will be met. In the USA requirements might come from federal regulations, such as the Gramm-Leach-Bliley Act [8], or from state laws, such as the California SB-1386 [9]. For organizations based in EU countries, both country-specific regulation and EU Directives may apply. For example, Directive 96/46/EC4 [10] makes it mandatory to treat personal data in applications with due care, whatever the application. 
<br>
'''Develop the Right Mindset'''<br>
Successfully testing an application for security vulnerabilities requires thinking "outside of the box." Normal use cases will test the normal behavior of the application when a user is using it in the manner that is expected. Good security testing requires going beyond what is expected and thinking like an attacker who is trying to break the application. Creative thinking can help to determine what unexpected data may cause an application to fail in an insecure manner. It can also help find what assumptions made by web developers are not always true and how they can be subverted. One of the reasons why automated tools are actually bad at automatically testing for vulnerabilities is that this creative thinking must be done on a case-by-case basis as most web applications are being developed in a unique way (even when using common frameworks). 
<br>
'''Understand the Subject'''<br>
One of the first major initiatives in any good security program should be to require accurate documentation of the application. The architecture, data-flow diagrams, use cases, etc, should be written in formal documents and made available for review. The technical specification and application documents should include information that lists not only the desired use cases, but also any specifically disallowed use case. Finally, it is good to have at least a basic security infrastructure that allows the monitoring and trending of attacks against an organization's applications and network (e.g., IDS systems). 
<br>
'''Use the Right Tools'''<br>
While we have already stated that there is no silver bullet tool, tools do play a critical role in the overall security program. There is a range of open source and commercial tools that can automate many routine security tasks. These tools can simplify and speed up the security process by assisting security personnel in their tasks. However, it is important to understand exactly what these tools can and cannot do so that they are not oversold or used incorrectly. 
<br>
'''The Devil is in the Details'''<br>
It is critical not to perform a superficial security review of an application and consider it complete. This will instill a false sense of confidence that can be as dangerous as not having done a security review in the first place. It is vital to carefully review the findings and weed out any false positive that may remain in the report. Reporting an incorrect security finding can often undermine the valid message of the rest of a security report. Care should be taken to verify that every possible section of application logic has been tested, and that every use case scenario was explored for possible vulnerabilities. 
<br>
'''Use Source Code When Available'''<br>
While black box penetration test results can be impressive and useful to demonstrate how vulnerabilities are exposed in a production environment, they are not the most effective or efficient way to secure an application. It is difficult for dynamic testing to test the entire code base, particularly if many nested conditional statements exist. If the source code for the application is available, it should be given to the security staff to assist them while performing their review. It is possible to discover vulnerabilities within the application source that would be missed during a black box engagement.  
<br>
'''Develop Metrics'''<br>
An important part of a good security program is the ability to determine if things are getting better. It is important to track the results of testing engagements, and develop metrics that will reveal the application security trends within the organization. 

Good metrics will show: <br>
*If more education and training are required;<br>
*If there is a particular security mechanism that is not clearly understood by the development team;<br>
*If the total number of security related problems being found each month is going down. 

Consistent metrics that can be generated in an automated way from available source code will also help the organization in assessing the effectiveness of mechanisms introduced to reduce security bugs in software development. Metrics are not easily developed, so using standard metrics like those provided by the OWASP Metrics project and other organizations is a good starting point.<br>
'''Document the Test Results'''<br>
To conclude the testing process, it is important to produce a formal record of what testing actions were taken, by whom, when they were performed, and details of the test findings. It is wise to agree on an acceptable format for the report which is useful to all concerned parties, which may include developers, project management, business owners, IT department, audit, and compliance. 

The report should be clear to the business owner in identifying where material risks exist and sufficient to get their backing for subsequent mitigation actions. The report should also be clear to the developer in pin-pointing the exact function that is affected by the vulnerability and associated recommendations for resolving issues in a language that the developer will understand. The report should also allow another security tester to reproduce the results. Writing the report should not be overly burdensome on the security tester themselves. Security testers are not generally renowned for their creative writing skills and agreeing on a complex report can lead to instances where test results do not get properly documented. Using a security test report template can save time and ensure that results are documented accurately and consistently, and are in a format that is suitable for the audience.
