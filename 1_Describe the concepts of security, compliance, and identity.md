
# Describe security and compliance concepts
 

## Describe Shared responsibility model

[Describe the shared responsibility model - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-security-concepts-methodologies/3-describe-shared-responsibility-model)

This model identifies which security tasks are handled by the cloud provider, and which are handled by customers. 

- On-premises - Organisation own 100% of responsibilities for Security and Compliance
- Cloud-based - Shared between customer and the cloud provider.

![The Shared responsibility model responsibilities by type](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-security-concepts-methodologies/media/3-shared-responsibility-model-responsibilites-type.png)

**Customer**,

- Owns **data and identities**.
- Is responsible for protecting the security of **data and identities**.


**Summary**

Responsibility is always retained by the customer organisation include,

- Information and Data
- Devices (Mobile and PCs)
- Accounts and Identities 

*In a shared responsibility model*, a layered approach to security is illustrated as: 

- For **on-premises solutions**, the customer is both accountable and responsible for all  aspects of security and operations.
- For **IaaS solutions**, the elements such as buildings, servers, networking hardware, and the  hypervisor should be managed by the platform vendor. The customer is responsible or  has a shared responsibility for securing and managing the operating system, network  configuration, applications, identity, clients, and data.
- For **PaaS solutions** build on IaaS deployments, and the provider is additionally responsible to  manage and secure the network controls. The customer is still responsible or has a  shared responsibility for securing and managing applications, identity, clients, and data.  
- For **SaaS solutions**, a vendor provides the application and abstracts customers from the  underlying components. Nonetheless, the customer continues to be accountable; they  must ensure that data is classified correctly, and they share a responsibility to manage  their users and end-point devices.   

The importance of understanding this shared responsibility model is essential for customers who  are moving to the cloud. **Cloud providers offer considerable advantages for security and  compliance efforts, but these advantages do not absolve the customer from protecting their  users, applications, and service offerings.** 

[Whitepaper](https://azure.microsoft.com/en-us/resources/shared-responsibility-for-cloud-computing/)


## Describe Defence in Depth

[Describe defense in depth - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-security-concepts-methodologies/4-describe-defense-depth)

Defence in depth uses a layered approach to security, rather than relying on a single perimeter. 

A defence in-depth strategy uses a series of mechanisms to slow the advance of an attack. Each layer provides protection so that, if one layer is breached, a subsequent layer will prevent an attacker getting unauthorized access to data.

Example layers of security might include:

- **Physical** security such as limiting access to a datacentre to only authorized personnel.
- **Identity and access** security controlling access to infrastructure and change control.
- **Perimeter** security including distributed denial of service (DDoS) protection to filter large-scale attacks before they can cause a denial of service for users.
- **Network** security can limit communication between resources using segmentation and access controls.
- The **compute** layer can secure access to virtual machines either on-premises or in the cloud by closing certain ports.
- **Application** layer security ensures that applications are secure and free of security vulnerabilities.
- **Data** layer security controls access to business and customer data, and encryption to protect data.

![Defense in depth uses multiple layers of security to protect sensitive data](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-security-concepts-methodologies/media/4-defense-depth.png)

Additional material 

[What is Defense in Depth | Benefits of Layered Security | Imperva](https://www.imperva.com/learn/application-security/defense-in-depth/)

[Azure Essentials: Defense in depth security - YouTube](https://www.youtube.com/watch?v=OTGMi0ksjXY)


## Describe Zero-Trust Methodology

[Describe the zero-trust methodology - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-security-concepts-methodologies/2-describe-zero-trust-methodology)

Assumes everything is on an open untrusted network. This model operates on **Trust no one, verify everything**. Putting this model in practice means, we no longer assume that a password is sufficient to validate a user, additional checks must be provided to prove identity like multi-factor authentication. Users are allowed only to the specific application or data they need.

#### Zero Trust Guiding Principals

- **Verify explicitly**
  - Always authenticate and authorise based on the available data points like Identity, Location, Device, Service or Workload, Data classification and Anomalies 
- **Least privileged access**
  - Limit access by JIT (**J**ust **I**n **T**ime) and **J**ust **E**nough **A**ccess (JEA)
  - Risk based adaptive policies
  - Data Protection, protecting both Data and Productivity
- **Assume breach**
  - Segment access by network, user devices and application.
  - User encryption to protect data.
  - Use of analysis to get visibility, detect threats and improve security.

#### Foundational Pillars

These six pillars work together with the Zero Trust model to enforce organisation security policies.

- **Identities**
- **Devices**
- **Applications**
- **Data**
- **Infrastructure**
- **Networks**


#### Confidentiality, Integrity, Availability (CIA)

- All three sides of the CIA model are important and they also represent trade-offs that need to be made.

![Confidentiality, Integrity, Availability (CIA)](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-security-concepts-methodologies/media/4-confidentiality-integrity-availability.png)

## Describe Encryption and Hashing

[Describe ways encryption hashing and signing can secure your data - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-security-concepts-methodologies/6-describe-ways-encryption-hashing-signing-secure-data)

Process of making data unreadable and unusable to unauthorised viewers. To be able to use or read encrypted data, it has to be decrypted, which requires use of a secret key.

Encryption can protect data at rest or in transit.

### Two types of top-level encryption

- #### Symmetric

  - Uses the same key to encrypt and decrypt the data.

-  Asymmetric

  - Uses public key and private key pair, either key can encrypt data but a single key can't be used to decrypt encrypted data.
  - Usually used for things like Transport Layer Security (TLS), HTTPS protocol and data signing.

### Encryption at rest

- Data at rest is data stored on a physical device like Server(s).
- It may be stored in database or Storage Account but, regardless of the device it is stored on, encryption of data at rest ensues the data is unreadable without the necessary keys and secrets to decrypt.

### Encryption in transit

- Data in transit is, the data moving from one location to another.
- This can be archived by encrypting the data at the Application layer before sending it over a network.
- Example of this type of encryption, **HTTPS**

### Hashing

- Hashing uses an algorithm to convert the original text to a *unique* fixed-length hash value. Each time the same text is hashed using the same algorithm, the same hash value is produced. That hash can then be used as a unique identifier of its associated data.

- Hashing is different to encryption in that it doesn't use keys, and the hashed value isn't subsequently decrypted back to the original.

- Hashing is used to store passwords. When a user enters their password, the same algorithm that created the stored hash creates a hash of the entered password. This is compared to the stored hashed version of the password. If they match, the user has entered their password correctly. This is more secure than storing plain text passwords, but hashing algorithms are also known to hackers. Because hash functions are deterministic (the same input produces the same output), hackers can use brute-force dictionary attacks by hashing the passwords. For every matched hash, they know the actual password. 
- To mitigate this risk, passwords are often **salted**. This refers to adding a fixed-length random value to the input of hash functions to create unique hashes for every input. As hackers can't know the salt value, the hashed passwords are more secure.

### Signing

![A private key generates the signature](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-security-concepts-methodologies/media/6-private-key-generates-signature.png)

There are two steps involved in creating a digital signature from a message. First, a hash value is created from the message. In the second step, the hash value is signed, using the signer's private key, as illustrated below:

![The message is hashed using a hashing algorithm, then signed](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-security-concepts-methodologies/media/6-hashed-using-hash-algorithm.png)

At the receiving end, the message is hashed again, and verified against the digital signature, which is decrypted using the public key.

![The hash value is verified against the signature using signer’s public key](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-security-concepts-methodologies/media/6-hash-value-verified.png)



## Microsoft Security and Compliance Principles

### Microsoft Privacy Principles

[Describe Microsoft's privacy principles - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-microsoft-security-compliance-principles/2-describe-microsofts-privacy-principles)

- Six key principles when Microsoft makes decision about data,
  - **Control**
    - Putting you, the customers, in control of your privacy with easy-to-use tools and clear choices.
  - **Transparency**
    - Being transparent about data collection and use so everyone can make informed decision.
  - **Security**
    - Protecting the data using strong security and encryption.
  - **Strong Legal Protections**
    - Respecting local privacy laws
    - Fighting for legal protection of privacy as a fundamental human right.
  - **No content-based targeting**
    - Not using email, chat, files or other personal content to target advertising.
  - **Benefits to you**
    - When data is collected, it is used to benefit the customer, to make the experience better.



### Offerings of the Service Trust Portal

[Describe the offerings of the Service Trust Portal - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-microsoft-security-compliance-principles/3-describe-offerings-of-service-trust-portal)

- The service trust portal provides Information, Tools and other resources about Microsoft Security, Privacy and Compliance practices.
- Site map
  - **Service Trust Portal**
    - Main menu
  - **Compliance Manager**
    - Measures progress in completing actions that help reduce risks around data protection and regulatory standards.
  - **Trust Documents**
    - Links to security implementation and design information.
  - **Industries and Regions**
    - Contains compliance information about Microsoft cloud services organised by industry and region.
  - **Trust Centre**
    - Links to Microsoft Trust Centre
  - **Resources**
    - FAQs, links to resources including information about the features and tools for Data Governance and Protection in Office 365 the Microsoft Global Datacentres.
  - **My Library**
    - Allow you to add documents and resources which are relevant to your organisation. You can also have email notification sent when a document is updated and one can also set frequency of how often you want to receive notifications.

[Interactive Guide - Explore Service Trust Portal](https://edxinteractivepage.blob.core.windows.net/edxpages/Security%20fundamentals/LP01M02%20Explore%20the%20Service%20Trust%20Portal/index.html)

[Azure compliance documentation | Microsoft Docs](https://docs.microsoft.com/en-us/azure/compliance/)

![Azure compliance documentation](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-microsoft-security-compliance-principles/media/4-azure-compliance-documentation.png)


## <u>Common Threats</u>

[Describe common threats - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-security-concepts-methodologies/5-describe-common-threats)

- **Data breach**
  
  - When some data is stolen, which involves personal data (data/information which can relate to identify an individual directly or indirectly)
- **Dictionary attack**
  - Type of an identity attack where a hacker attempts to steal an identity by trying a large number of known passwords.
  - *Passwords are tried against a known username.*
  - This attacks are also known as **Brute Force Attacks**.
- **Ransomware**
  - Type of a malware that encrypts files and folders, preventing access to important files.
  - These attacks attempts to extort money from victims, usually in the form of cryptocurrencies, in the exchange of decryption key.
- **Disruptive attacks**
  - A **D**istributed **D**enial **o**f **S**ervice (DDoS) attack attempts to exhaust an application's resources, making the application unavailable to legitimate users.
  - These types of attacks can be targeted at any endpoints which are publicly reachable through Internet.

- **Other types**

  - Coin Miners

  - Rootkits

    - These attacks intercept and change standard Operating System processes.
    - Once a device is infected with these type of an attack, reports coming from the devices can not be trusted.

  - Trojans

    - Type of malware, which can not spread on their own.
    - Either they have to be downloaded manually or another malware needs to download and install them.
    - Trojan uses the same file name as real and legitimate apps, so it's easy for a user to accidentally download instead.

  -  Worms

    - Type of malware, which can copy itself and spread through a network by exploiting vulnerabilities.
    - Usually spreads through e-mail attachment, text messages, file sharing programs, social networking sites, network shares, removable drive etc.

  - Exploits and Exploit Kits.

    
# Define identity concepts

## Identity as the primary security perimeter

[Define Identity as the primary security perimeter - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-identity-principles-concepts/3-define-identity-primary-security-perimeter)

- The traditional perimeter based security model is no longer enough. Identity has become the new security perimeter that enables organisations to secure their assets.
- Enterprise security needs to adapt new reality, security perimeter can no longer be viewed as on-premises network, it now extends to,
  - SaaS app for business critical work may be hosted outside the corporate network.
  - BYOD devices that employees are using to access corporate network while working from home.
  - Unmanaged device that a customer or partner is using to access corporate data or collaborating with employees.
  - IoT devices installed throughout your corporate network and inside customer locations.

![Identity is the new security perimeter](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-identity-principles-concepts/media/3-identity-new-security-perimeter.png)

### Four Pillars of Identity

Addressing following four pillars is key to a comprehensive and robust identity and access control situation.

1. Administration
2. Authentication
3. Authorisation
4. Auditing


### Common Identity Attacks

[Describe common identity attacks - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-identity-principles-concepts/2-describe-common-identity-attacks)

- Some of the most common types of security threats that organisation face today.

- Design to steal credentials to authenticate that someone or something is who they are claiming to be, resulting in Identity Theft.

- To protect against such Identity attacks, robust security and monitoring is needed. ***Risk detections in Azure AD Identity Protection include identified suspicious actions related to user accounts.***

- There are **two types of Risk,**

  - **User Risk**
    - Represent the probability that a given identity or account is compromised.
  - **Sign-in Risk**
    - Represent the probability that a given authentication request is not authorised by the identity owner.

  #### Password-based Attacks

  ![Password spray attack](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-identity-principles-concepts/media/2-password-spray-attack.png)

  - This includes Password spray attacks and Brute force attacks.
    - ***Password Spray Attack***, this attack attempts to match a username against a list of weak passwords
    - ***Brute Force Attack***, this attack try many passwords against one or more accounts, sometimes using dictionaries of commonly used passwords. 

  #### Phishing Attack

  - A phishing attack is when a hacker sends an email that appears to come from a reputable source. 

  #### Spear Phishing Attack

  - A spear phishing scam is a variant on Phishing. Hackers build databases of information about users, which can be used to create highly credible emails. The email may appear to have come from someone in your organisation who is requesting information. 

## Define Authentication (AuthN)

Identity authentication determines if the person is who they say they are. Authentication relies on additional data that is difficult to produce, except by that specific person.

[What is Authentication - YouTube](https://www.youtube.com/watch?v=927KdwZZoU0)

[Identity Authentication – Are They Who They Say They Are? (trulioo.com)](https://www.trulioo.com/blog/identity-authentication)

## Define Authorisation (AuthZ)

Authorization is the process of giving someone the ability to access a resource.

[What is Authorization? - Examples and definition - Auth0](https://auth0.com/intro-to-iam/what-is-authorization/)



### Modern Authentication

[Describe modern authentication and the role of the identity provider - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-identity-principles-concepts/4-describe-modern-authentication-role-identity-provider)

- Morden authentication is an umbrella term for AuthN and AuthZ methods between a client, such as your laptop or phone, and a server, like a website or application.

  

## Describe Identity Providers (IdP) 

[Describe modern authentication and the role of the identity provider - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-identity-principles-concepts/4-describe-modern-authentication-role-identity-provider)

- Identity Provider (IdP) is the role at the centre of modern authentication.

- All services including all AuthN services are supplied by a central Identity Provider. Information that is used to authenticate the user with the server is stored and managed centrally by the Identity Provider (IdP).

- With a central identity provider, organizations can establish authentication and authorization policies, monitor user behaviour, identify suspicious activities, and reduce malicious attacks.

- Microsoft Azure Active Directory is an example of a cloud-based identity provider. Other examples include Twitter, Google, Amazon, LinkedIn, and GitHub.

- Another fundamental capability of an identity provider (IdP) and “modern authentication” is the support for single sign-on (SSO). With SSO, the user logs in once and that credential is used to access multiple applications or resources. When you set up SSO between multiple identity providers, it's called federation.

  

## Describe Federated Services

[Describe the concept of Federated Services - Learn | Microsoft Docs](https://docs.microsoft.com/en-au/learn/modules/describe-identity-principles-concepts/5-describe-concept-federated-services)

- Federation enables the access of services across organizational or domain boundaries by establishing trust relationships between the respective domain’s identity provider. With federation, there's no need for a user to maintain a different username and password when accessing resources in other domains.

![Simplifed view of how federation works](https://docs.microsoft.com/en-au/learn/wwl-sci/describe-identity-principles-concepts/media/5-federated-identification.png)

- The simplified way to think about this federation scenario is as follows:
  - The website uses the authentication services of IdP-A.
  - The user authenticates with IdP-B.
  - IdP-A has a trust relationship configured with IdP-B.
  - When the user’s credentials are passed to the website, the website trusts the user and allows access.
- **With federation, trust isn't always bidirectional. Although IdP-A may trust IdP-B and allow the user in domain B to access the website in domain A, the opposite isn't true, unless that trust relationship is configured.**
- A common example of federation in practice is when a user logs in to a third-party site with their social media account, such as Twitter. In this scenario, Twitter is an identity provider, and the third-party site might be using a different identity provider, such as Azure AD. There's a trust relationship between Azure AD and Twitter.


