=== The OWASP Testing Project ===
----
The OWASP Testing Project has been in development for many years. The aim of the project is to help people understand the ''what'', ''why'', ''when'', ''where'', and ''how'' of testing web applications. The project has delivered a complete testing framework, not merely a simple checklist or prescription of issues that should be addressed. Readers can use this framework as a template to build their own testing programs or to qualify other people’s processes. The Testing Guide describes in detail both the general testing framework and the techniques required to implement the framework in practice.

Writing the Testing Guide has proven to be a difficult task. It was a challenge to obtain consensus and develop content that allowed people to apply the concepts described in the guide, while also enabling them to work in their own environment and culture. It was also a challenge to change the focus of web application testing from penetration testing to testing integrated in the software development life cycle. 

However, the group is very satisfied with the results of the project. Many industry experts and security professionals, some of whom are responsible for software security at some of the largest companies in the world, are validating the testing framework. This framework helps organizations test their web applications in order to build reliable and secure software. The framework does not simply highlighting areas of weakness, although the latter is certainly a by product of many of the OWASP guides and checklists. As such, hard decisions had to be made about the appropriateness of certain testing techniques and technologies. The group fully understands that not everyone will agree upon all of these decisions. However, OWASP is able to take the high ground and change culture over time through awareness and education based on consensus and experience.

The rest of this guide is organized as follows:
This introduction covers the pre-requisites of testing web applications and the scope of testing. It also covers the principles of successful testing and testing techniques. 
Chapter 3 presents the OWASP Testing Framework and explains its techniques and tasks in relation to the various phases of the software development life cycle. 
Chapter 4 covers how to test for specific vulnerabilities (e.g., SQL Injection) by code inspection and penetration testing. 

'''Measuring Security: the Economics of Insecure Software'''<br>
A basic tenet of software engineering is that you can't control what you can't measure [1]. Security testing is no different. Unfortunately, measuring security is a notoriously difficult process. This topic will not be covered in detail here, as it would take a guide on its own (for an introduction, see [2]). 

One aspect that should be emphasized is that security measurements are about both the specific technical issues (e.g., how prevalent a certain vulnerability is) and how these issues affect the economics of software. Most technical people will at least understand the basic issues, or they may have a deeper understanding of the vulnerabilities. Sadly, few are able to translate that technical knowledge into monetary terms and quantify the potential cost of vulnerabilities to the application owner's business. Until this happens, CIOs will not be able to develop an accurate return on security investment and, subsequently, assign appropriate budgets for software security.<br/>

While estimating the cost of insecure software may appear a daunting task, there has been a significant amount of work in this direction. For example, in June 2002, the US National Institute of Standards (NIST) published a survey on the cost of insecure software to the US economy due to inadequate software testing [3]. Interestingly, they estimate that a better testing infrastructure would save more than a third of these costs, or about $22 billion a year. More recently, the links between economics and security have been studied by academic researchers. See [4] for more information about some of these efforts.

The framework described in this document encourages people to measure security throughout the entire development process. They can then relate the cost of insecure software to the impact it has on the business, and consequently develop appropriate business processes and assign resources to manage the risk. Remember that measuring and testing web applications is even more critical than for other software, since web applications are exposed to millions of users through the Internet.

'''What is Testing?'''<br>
During the development life cycle of a web application many things need to be tested, but what does testing actually mean? The Merriam-Webster Dictionary describes testing as: 
* To put to test or proof. 
* To undergo a test. 
* To be assigned a standing or evaluation based on tests. 
For the purposes of this document testing is a process of comparing the state of a system or application against a set of criteria. In the security industry people frequently test against a set of mental criteria that are neither well defined nor complete. As a result of this, many outsiders regard security testing as a black art. The aim of this document is to change that perception and to make it easier for people without in-depth security knowledge to make a difference in testing.

'''Why Perform Testing?'''<br>
This document is designed to help organizations understand what comprises a testing program, and to help them identify the steps that need to be undertaken to build and operate a testing program on web applications. The guide gives a broad view of the elements required to make a comprehensive web application security program. This guide can be used as a reference guide and as a methodology to help determine the gap between existing practices and industry best practices. This guide allows organizations to compare themselves against industry peers, to understand the magnitude of resources required to test and maintain software, or to prepare for an audit. This chapter does not go into the technical details of how to test an application, as the intent is to provide a typical security organizational framework. The technical details about how to test an application, as part of a penetration test or code review, will be covered in the remaining parts of this document. 

'''When to Test?'''<br>
Most people today don’t test software until it has already been created and is in the deployment phase of its life cycle (i.e., code has been created and instantiated into a working web application). This is generally a very ineffective and cost-prohibitive practice. One of the best methods to prevent security bugs from appearing in production applications is to improve the Software Development Life Cycle (SDLC) by including security in each of its phases. An SDLC is a structure imposed on the development of software artefacts. If an SDLC is not currently being used in your environment, it is time to pick one! The following figure shows a generic SDLC model as well as the (estimated) increasing cost of fixing security bugs in such a model. 

<center>[[Image:SDLC.jpg]]<br>
''Figure 1: Generic SDLC Model'' </center>

Companies should inspect their overall SDLC to ensure that security is an integral part of the development process. SDLCs should include security tests to ensure security is adequately covered and controls are effective throughout the development process. 

'''What to Test?'''<br>
It can be helpful to think of software development as a combination of people, process, and technology. If these are the factors that "create" software, then it is logical that these are the factors that must be tested. Today most people generally test the technology or the software itself. 

An effective testing program should have components that test:<br>
*''People'' – to ensure that there is adequate education and awareness;<br>
*''Process'' – to ensure that there are adequate policies and standards and that people know how to follow these policies;<br> *''Technology'' – to ensure that the process has been effective in its implementation. 

Unless a holistic approach is adopted, testing just the technical implementation of an application will not uncover management or operational vulnerabilities that could be present. By testing the people, policies, and processes, an organization can catch issues that would later manifest themselves into defects in the technology, thus eradicating bugs early and identifying the root causes of defects. Likewise, testing only some of the technical issues that can be present in a system will result in an incomplete and inaccurate security posture assessment. 

Denis Verdon, Head of Information Security at [http://www.fnf.com Fidelity National Financial] presented an excellent analogy for this misconception at the OWASP AppSec 2004 Conference in New York [5]: "If cars were built like applications [...] safety tests would assume frontal impact only. Cars would not be roll tested, or tested for stability in emergency maneuvers, brake effectiveness, side impact, and resistance to theft." <br>

'''Feedback and Comments'''<br>
As with all OWASP projects, we welcome comments and feedback. We especially like to know that our work is being used and that it is effective and accurate.
