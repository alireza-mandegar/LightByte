+++
date = '2025-02-17T13:50:45+03:30'
draft = false
title = 'Softwarevulnerabilities'
+++

# Categorizing Software Vulnerabilities

### BUFFER OVERFLOW

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/e3a11f600245ed0107323cc592db6b78a32fd24b.png)

Buffers are memory areas allocated to an application. A vulnerability occurs when data is written beyond the limits of a buffer. By changing data beyond the boundaries of a buffer, the application can access memory allocated to other processes. This can lead to a system crash or data compromise, or provide escalation of privileges.

### NON-VALIDATED INPUT

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/f73c8e938c60bc30ef44706253c7ce4e22d6bb63.png)

Programs often require data input, but this incoming data could have malicious content, designed to force the program to behave in an unintended way.

For example, consider a program that receives an image for processing. A malicious user could craft an image file with invalid image dimensions. The maliciously crafted dimensions could force the program to allocate buffers of incorrect and unexpected sizes.

### RACE CONDITIONS

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/f09be8c7887ba369fe1e2c8d630a5048b1943e7a.png)

This vulnerability describes a situation where the output of an event depends on ordered or timed outputs. A race condition becomes a source of vulnerability when the required ordered or timed events do not occur in the correct order or at the proper time.

### WEAKNESSES IN SECURITY PRACTICES

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/c3d396dc995e72bf0cbea4b36f0208f3ea344292.png)

Systems and sensitive data can be protected through techniques such as authentication, authorization and encryption. Developers should stick to using security techniques and libraries that have already been created, tested and verified and should not attempt to create their own security algorithms. These will only likely introduce new vulnerabilities.

### ACCESS CONTROL PROBLEMS

![](https://www.netacad.com/content/i2cs/7.1/courses/content/m2/en-US/assets/93a2ad5fecc5430041b8d9c7184f4a6c89708e80.png)

Access control is the process of controlling who does what and ranges from managing physical access to equipment to dictating who has access to a resource, such as a file, and what they can do with it, such as read or change the file. Many security vulnerabilities are created by the improper use of access controls.

Nearly all access controls and security practices can be overcome if an attacker has physical access to target equipment. For example, no matter the permission settings on a file, a hacker can bypass the operating system and read the data directly off the disk. Therefore, to protect the machine and the data it contains, physical access must be restricted, and encryption techniques must be used to protect data from being stolen or corrupted.
