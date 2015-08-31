==Testing Techniques Explained==

This section presents a high-level overview of various testing techniques that can be employed when building a testing program. It does not present specific methodologies for these techniques as this information is covered in Chapter 3. This section is included to provide context for the framework presented in the next chapter and to highlight the advantages and disadvantages of some of the techniques that should be considered. In particular, we will cover:
* Manual Inspections & Reviews 
* Threat Modeling 
* Code Review 
* Penetration Testing 

=== Manual Inspections & Reviews ===
'''Overview'''<br>
Manual inspections are human reviews that typically test the security implications of people, policies, and processes. Manual inspections can also include inspection of technology decisions such as architectural designs. They are usually conducted by analyzing documentation or performing interviews with the designers or system owners. 

While the concept of manual inspections and human reviews is simple, they can be among the most powerful and effective techniques available. By asking someone how something works and why it was implemented in a specific way, the tester can quickly determine if any security concerns are likely to be evident. Manual inspections and reviews are one of the few ways to test the software development life-cycle process itself and to ensure that there is an adequate policy or skill set in place. 

As with many things in life, when conducting manual inspections and reviews it is recommended that a trust-but-verify model is adopted. Not everything that the tester is shown or told will be accurate. Manual reviews are particularly good for testing whether people understand the security process, have been made aware of policy, and have the appropriate skills to design or implement a secure application. 

Other activities, including manually reviewing the documentation, secure coding policies, security requirements, and architectural designs, should all be accomplished using manual inspections.

'''Advantages:'''
* Requires no supporting technology 
* Can be applied to a variety of situations
* Flexible 
* Promotes teamwork 
* Early in the SDLC 

'''Disadvantages:'''
* Can be time consuming 
* Supporting material not always available 
* Requires significant human thought and skill to be effective

=== Threat Modeling ===
'''Overview'''<br>
Threat modeling has become a popular technique to help system designers think about the security threats that their systems and applications might face. Therefore, threat modeling can be seen as risk assessment for applications. In fact, it enables the designer to develop mitigation strategies for potential vulnerabilities and helps them focus their inevitably limited resources and attention on the parts of the system that most require it. It is recommended that all applications have a threat model developed and documented. Threat models should be created as early as possible in the SDLC, and should be revisited as the application evolves and development progresses. 

To develop a threat model, we recommend taking a simple approach that follows the NIST 800-30 [11] standard for risk assessment. This approach involves: 
* Decomposing the application – use a process of manual inspection to understand how the application works, its assets, functionality, and connectivity. 
* Defining and classifying the assets – classify the assets into tangible and intangible assets and rank them according to business importance. 
* Exploring potential vulnerabilities - whether technical, operational, or management. 
* Exploring potential threats – develop a realistic view of potential attack vectors from an attacker’s perspective, by using threat scenarios or attack trees.
* Creating mitigation strategies – develop mitigating controls for each of the threats deemed to be realistic. 

The output from a threat model itself can vary but is typically a collection of lists and diagrams. The OWASP Code Review Guide outlines an Application Threat Modeling methodology that can be used as a reference for the testing applications for potential security flaws in the design of the application. There is no right or wrong way to develop threat models and perform information risk assessments on applications. [12]. <br>

'''Advantages:'''
* Practical attacker's view of the system 
* Flexible 
* Early in the SDLC 

'''Disadvantages: <br>'''
* Relatively new technique 
* Good threat models don’t automatically mean good software

=== Source Code Review ===
'''Overview'''<br>
Source code review is the process of manually checking the source code of a web application for security issues. Many serious security vulnerabilities cannot be detected with any other form of analysis or testing. As the popular saying goes “if you want to know what’s really going on, go straight to the source." Almost all security experts agree that there is no substitute for actually looking at the code. All the information for identifying security problems is there in the code somewhere. Unlike testing third party closed software such as operating systems, when testing web applications (especially if they have been developed in-house) the source code should be made available for testing purposes. 

Many unintentional but significant security problems are also extremely difficult to discover with other forms of analysis or testing, such as penetration testing, making source code analysis the technique of choice for technical testing. With the source code, a tester can accurately determine what is happening (or is supposed to be happening) and remove the guess work of black box testing. 

Examples of issues that are particularly conducive to being found through source code reviews include concurrency problems, flawed business logic, access control problems, and cryptographic weaknesses as well as backdoors, Trojans, Easter eggs, time bombs, logic bombs, and other forms of malicious code. These issues often manifest themselves as the most harmful vulnerabilities in web sites. Source code analysis can also be extremely efficient to find implementation issues such as places where input validation was not performed or when fail open control procedures may be present. But keep in mind that operational procedures need to be reviewed as well, since the source code being deployed might not be the same as the one being analyzed herein [13].<br>

'''Advantages:'''
* Completeness and effectiveness 
* Accuracy 
* Fast (for competent reviewers) 

'''Disadvantages:'''
* Requires highly skilled security developers 
* Can miss issues in compiled libraries 
* Cannot detect run-time errors easily 
* The source code actually deployed might differ from the one being analyzed

'''For more on code review, checkout the [[OWASP Code Review Project|OWASP code review project]]'''.<BR>

=== Penetration Testing ===
'''Overview'''<br>
Penetration testing has been a common technique used to test network security for many years. It is also commonly known as black box testing or ethical hacking. Penetration testing is essentially the “art” of testing a running application remotely to find security vulnerabilities, without knowing the inner workings of the application itself. Typically, the penetration test team would have access to an application as if they were users. The tester acts like an attacker and attempts to find and exploit vulnerabilities. In many cases the tester will be given a valid account on the system. 

While penetration testing has proven to be effective in network security, the technique does not naturally translate to applications. When penetration testing is performed on networks and operating systems, the majority of the work is involved in finding and then exploiting known vulnerabilities in specific technologies. As web applications are almost exclusively bespoke, penetration testing in the web application arena is more akin to pure research. Penetration testing tools have been developed that automate the process, but with the nature of web applications their effectiveness is usually poor. 

Many people today use web application penetration testing as their primary security testing technique. Whilst it certainly has its place in a testing program, we do not believe it should be considered as the primary or only testing technique. Gary McGraw in [14] summed up penetration testing well when he said, “If you fail a penetration test you know you have a very bad problem indeed. If you pass a penetration test you do not know that you don’t have a very bad problem”. However, focused penetration testing (i.e., testing that attempts to exploit known vulnerabilities detected in previous reviews) can be useful in detecting if some specific vulnerabilities are actually fixed in the source code deployed on the web site. <br>

'''Advantages:'''
* Can be fast (and therefore cheap) 
* Requires a relatively lower skill-set than source code review 
* Tests the code that is actually being exposed 

'''Disadvantages:'''
* Too late in the SDLC 
* Front impact testing only.

=== The Need for a Balanced Approach ===
With so many techniques and approaches to testing the security of web applications it can be difficult to understand which techniques to use and when to use them. Experience shows that there is no right or wrong answer to the question of exactly what techniques should be used to build a testing framework. In fact all techniques should probably be used to test all the areas that need to be tested. 

Although it is clear that there is no single technique that can be performed to effectively cover all security testing and ensure that all issues have been addressed, many companies adopt only one approach. The approach used has historically been penetration testing. Penetration testing, while useful, cannot effectively address many of the issues that need to be tested. It is simply “too little too late” in the software development life cycle (SDLC). 

The correct approach is a balanced approach that includes several techniques, from manual reviews to technical testing. A balanced approach should cover testing in all phases of the SDLC. This approach leverages the most appropriate techniques available depending on the current SDLC phase. 

Of course there are times and circumstances where only one technique is possible. For example, a test on a web application that has already been created, but where the testing party does not have access to the source code. In this case, penetration testing is clearly better than no testing at all. However, the testing parties should be encouraged to challenge assumptions, such as no access to source code, and to explore the possibility of more complete testing. 

A balanced approach varies depending on many factors, such as the maturity of the testing process and corporate culture. It is recommended that a balanced testing framework should look something like the representations shown in Figure 3 and Figure 4. The following figure shows a typical proportional representation overlaid onto the software development life cycle. In keeping with research and experience, it is essential that companies place a higher emphasis on the early stages of development.
<center>
[[Image:ProportionSDLC.png]]
<br>''Figure 3: Proportion of Test Effort in SDLC''
</center>
The following figure shows a typical proportional representation overlaid onto testing techniques. <br>
<center>
[[Image:ProportionTest.png]]
<br>''Figure 4: Proportion of Test Effort According to Test Technique''
</center>

'''A Note about Web Application Scanners'''<br>
Many organizations have started to use automated web application scanners. While they undoubtedly have a place in a testing program, some fundamental issues need to be highlighted about why it is believed that automating black box testing is not (or will ever be) effective. However, highlighting these issues should not discourage the use of web application scanners. Rather, the aim is to ensure the limitations are understood and testing frameworks are planned appropriately.

Important: OWASP is currently working to develop a web application scanner bench marking platform. The following examples show why automated black box testing is not effective. 
<br>
''''Example 1: Magic Parameters''''<br>
Imagine a simple web application that accepts a name-value pair of “magic” and then the value. For simplicity, the GET request may be: ''<nowiki>http://www.host/application?magic=value</nowiki>'' <br> To further simplify the example, the values in this case can only be ASCII characters a – z (upper or lowercase) and integers 0 – 9. 

The designers of this application created an administrative backdoor during testing, but obfuscated it to prevent the casual observer from discovering it. By submitting the value sf8g7sfjdsurtsdieerwqredsgnfg8d (30 characters), the user will then be logged in and presented with an administrative screen with total control of the application. The HTTP request is now:<br> ''<nowiki>http://www.host/application?magic= sf8g7sfjdsurtsdieerwqredsgnfg8d </nowiki>'' <br>

Given that all of the other parameters were simple two- and three-characters fields, it is not possible to start guessing combinations at approximately 28 characters. A web application scanner will need to brute force (or guess) the entire key space of 30 characters. That is up to 30^28 permutations, or trillions of HTTP requests. That is an electron in a digital haystack. 

The code for this exemplar Magic Parameter check may look like the following: <br>
 public void doPost( HttpServletRequest request, HttpServletResponse response) 
 { 
 String magic = “sf8g7sfjdsurtsdieerwqredsgnfg8d”; 
 boolean admin = magic.equals( request.getParameter(“magic”));
 if (admin) doAdmin( request, response); 
 else …. // normal processing 
 } 
By looking in the code, the vulnerability practically leaps off the page as a potential problem. 
<br>
'''Example 2: Bad Cryptography'''<br>
Cryptography is widely used in web applications. Imagine that a developer decided to write a simple cryptography algorithm to sign a user in from site A to site B automatically. In his/her wisdom, the developer decides that if a user is logged into site A, then he/she will generate a key using an MD5 hash function that comprises: ''Hash { username : date }'' <br>
When a user is passed to site B, he/she will send the key on the query string to site B in an HTTP re-direct. Site B independently computes the hash, and compares it to the hash passed on the request. If they match, site B signs the user in as the user they claim to be. 

As the scheme is explained the inadequacies can be worked out. Anyone that figures out the scheme (or is told how it works, or downloads the information from Bugtraq) can log in as any user. Manual inspection, such as a review or code inspection, would have uncovered this security issue quickly. A black-box web application scanner would not have uncovered the vulnerability. It would have seen a 128-bit hash that changed with each user, and by the nature of hash functions, did not change in any predictable way.
<br>
'''A Note about Static Source Code Review Tools'''<br>
Many organizations have started to use static source code scanners. While they undoubtedly have a place in a comprehensive testing program, it is necessary to highlight some fundamental issues about why this approach is not effective when used alone. Static source code analysis alone cannot identify issues due to flaws in the design, since it cannot understand the context in which the code is constructed. Source code analysis tools are useful in determining security issues due to coding errors, however significant manual effort is required to validate the findings. 
<br>
