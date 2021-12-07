# NIST Perspective

In order to have successful service delivery, the US Government (USG) needs to ensure the
<span style="color:blue">***reliability***</span> in the delivery of products and processes. By ensuring durable and
proper standards in place for cloud computing in security, data portability and service interoperability, the USG will
have the additional confidence needed to move their applications into the cloud
[[ref](https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=909505)].

Outlined problems:
* Service Deployment
  * Public Cloud
  * On-site Private Cloud
  * Outsourced Private Cloud
  * On-site Community Cloud
  * Outsourced Community Cloud
  * Hybrid Cloud
* Service Orchestration
* Cloud Service Management
* Business Support
  * Customer management
  * Contract management
  * Inventory Management
  * Accounting and Billing
  * Reporting and Auditing
  * Pricing and Rating
* Provisioning and Configuration
  * Rapid provisioning
  * Resource changing
  * Monitoring and Reporting
  * Metering
  * SLA management
* Portability and Interoperability
* Security
* Shared Security Responsibilities
* Privacy

The NIST Cloud Computing Standards Roadmap Working Group has surveyed the existing standards landscape for
interoperability, performance, portability, security, and accessibility standards/models/studies/use cases/conformity
assessment programs, etc., relevant to cloud computing. Where possible, new and emerging standardization work has also
been tracked and surveyed [[ref](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.500-291r2.pdf)].

## What is Cloud Computing?

Cloud computing is a model for enabling ubiquitous, convenient, on-demand network access to a shared pool of
configurable computing resources (e.g., networks, servers, storage, applications, and services) that can be rapidly
provisioned and released with minimal management effort or service provider interaction. This cloud model is composed
of five essential characteristics, three service models, and four deployment models.

Essential Characteristics:
* On-demand self-service
* Broad network access
* Resource pooling
* Rapid elasticity
* Measured service

Service Models:
* Software as a Service (SaaS)
* Platform as a Service (PaaS)
* Infrastructure as a Service (IaaS)

Deployment Models:
* Private cloud
* Community cloud
* Public cloud
* Hybrid cloud

## Use Cases and Challenges

For security auditing, a cloud auditor can make an assessment of the security controls in the information system to
determine the extent to which the controls are implemented correctly, operating as intended, and producing the desired
outcome with respect to the security requirements for the system. The security auditing should include the verification
of the compliance with regulation and security policy.

Technical use-cases:
* Single Cloud System
  * Deployment on a single cloud system
  * Manage resources on a single cloud system
  * Interface enterprise systems to a single cloud system
  * Enterprise systems migrated or replaced on a single cloud system
* Multiple Cloud Systems (serially, one at a time)
  * Migration between cloud systems
  * Interface across multiple cloud systems
  * Work with a selected cloud system
* Multiple Cloud Systems – (simultaneously, more than one at a time)
  * Operate across multiple cloud systems

Spectrum of cloud computing use cases:
* Centralized vs. Distributed, and
* Within vs. Crossing Trust Boundaries

Common technical requirements:
* Creating, accessing, updating, deleting data objects in cloud systems;
* Moving VMs and virtual appliances between cloud systems;
* Selecting the best IaaS vendor for private externally hosted cloud system;
* Tools for monitoring and managing multiple cloud systems;
* Migrating data between cloud systems;
* Single sign-on access to multiple cloud systems;
* Orchestrated processes across cloud systems;
* Discovering cloud resources;
* Evaluating SLAs and penalties; and
* Auditing cloud systems.

Possible types of security challenges for cloud computing services include the following:
* Compromises to the confidentiality and integrity of data in transit to and from a cloud provider and at rest;
* Attacks which take advantage of the homogeneity and power of cloud computing systems to rapidly scale and increase the
  magnitude of the attack;
* A consumer’s unauthorized access (through improper authentication or authorization, or exploit of vulnerabilities
  introduced maliciously or unintentionally) to software, data, and resources provisioned to, and owned by another
  authorized cloud consumer;
* Increased levels of network-based attacks that exploit software not designed for an Internet-based model and
  vulnerabilities existing in resources formerly accessed through private networks;
* Limited ability to encrypt data at rest in a multi-tenancy environment;
* Portability constraints resulting from the lack of standardization of cloud services application programming
  interfaces (APIs) that preclude cloud consumers to easily migrate to a new cloud service provider when availability
  requirements are not met;
* Attacks that exploit the physical abstraction of cloud resources and exploit a lack of transparency in audit procedures
  or records;
* Attacks that take advantage of known, older vulnerabilities in virtual machines that have not been properly updated
  and patched;
* Attacks that exploit inconsistencies in global privacy policies and regulations;
* Attacks that exploit cloud computing supply chain vulnerabilities to include those that occur while cloud computing
  components are in transit from the supplier to the cloud service provider;
* Insider abuse of their privileges, especially cloud provider’s personnel in high risk roles (e.g. system
  administrators); and
* Interception of data in transit (man-in-the-middle attacks).

Some of the main security objectives for a cloud computing implementer should include:
* Protect consumers’ data from unauthorized access, disclosure, modification or monitoring. This includes supporting
  identity management and access control policies for authorized users accessing cloud services. This includes the
  ability of a customer to make access to its data selectively available to other users.
* Prevent unauthorized access to cloud computing infrastructure resources. This includes implementing security domains
  that have logical separation between computing resources (e.g. logical separation of customer workloads running on the
  same physical server by VM monitors [hypervisors] in a multi-tenant environment) and using secure-by-default
  configurations.
* Deploy in the cloud web applications designed and implemented for an Internet threat model.
* Challenges to prevent Internet browsers using cloud computing from attacks to mitigate end-user security
  vulnerabilities. This includes taking measures to protect internet- connected personal computing devices by applying
  security software, personal firewalls, and patch maintenance.
* Include access control and intrusion detection and prevention solutions in cloud computing implementations and conduct
  an independent assessment to verify that the solutions are installed and functional. This includes traditional
  perimeter security measures in combination with the domain security model. Traditional perimeter security includes
  restricting physical access to network and devices; protecting individual components from exploitation through
  security patch deployment; setting as default most secure configurations; disabling all unused ports and services;
  using role-based access control; monitoring audit trails; minimizing privileges to minimum necessary; using antivirus
  software; and encrypting communications.
* Define trust boundaries between cloud provider(s) and consumers to ensure that the responsibilities to implement
  security controls are clearly identified.
* Implement standardized APIs for interoperability and portability to support easy migration of consumers’ data to other
  cloud providers when necessary.

## Existing Standards

### Security

Authentication & Authorization:
* RFC 5246, Secure Sockets Layer (SSL)/ Transport, Layer Security (TLS)
* RFC 3820, X.509, Public Key Infrastructure (PKI) Proxy Certificate Profile
* RFC5280, Internet X.509, Public Key Infrastructure Certificate and, Certificate Revocation List (CRL) Profile
* RFC 5849, OAuth (Open Authorization Protocol)
* ISO/IEC 9594-8:2008 | X.509, Information technology -- Open Systems Interconnection -- The Directory, Public-key and
  attribute certificate frameworks
* ISO/IEC 29115 | X.1254, Information technology -- Security techniques -- Entity authentication assurance framework
* FIPS 181, Automated Password Generator
* FIPS 196, Entity Authentication Using Public Key Cryptography
* OpenID Authentication
* eXtensible, Access Control Markup Language (XACML)
* Security Assertion Markup Language (SAML)

Confidentiality:
* RFC 5246, Secure Sockets Layer (SSL)/ Transport Layer Security (TLS)
* Key Management Interoperability Protocol (KMIP)
* XML Encryption Syntax and Processing
* FIPS 140-2, Security Requirements for Cryptographic Modules
* FIPS 185, Escrowed Encryption Standard (EES)
* FIPS 197, Advanced Encryption Standard (AES)
* FIPS 188, Standard Security Label for Information Transfer

Integrity:
* XML signature (XMLDSig)
* FIPS 180-4, Secure Hash Standard (SHS)
* FIPS 186-4, Digital Signature Standard (DSS)
* FIPS 198-1, The Keyed-Hash Message Authentication Code (HMAC)

Identity Management:
* X.idmcc, Requirement of IdM in Cloud Computing
* FIPS 201-1, Personal Identity Verification (PIV) of Federal Employees and Contractors
* Service Provisioning Markup Language (SPML)
* Web Services Federation Language (WS-Federation) Version 1.2
* WS-Trust 1.3
* Security Assertion Markup Language (SAML)
* OpenID Authentication 1.1

Security Monitoring & Incident Response:
* ISO/IEC WD 27035-1, Information technology -- Security techniques -- Information security incident management --
  Part 1: Principles of incident management
* ISO/IEC WD 27035-3, Information technology -- Security techniques -- Information security incident management --
  Part 3: Guidelines for CSIRT operations
* ISO/IEC WD 27039, Information technology -- Security techniques -- Selection, deployment and operations of intrusion
  detection systems
* ISO/IEC 18180, Information technology - Specification for the Extensible Configuration Checklist Description Format
  (XCCDF) Version 1.2 (NIST IR 7275)
* X.1500, Cybersecurity information exchange techniques
* X.1520, Common vulnerabilities and exposures
* X.1521, Common Vulnerability Scoring System
* PCI Data Security Standard
* FIPS 191, Guideline for the Analysis of Local Area Network Security

Security Controls:
* Cloud Controls Matrix Version 1.3
* ISO/IEC 27001:2005, Information Technology – Security Techniques Information Security Management Systems Requirements
* ISO/IEC WD TS 27017, Information technology -- Security techniques -- Information security management - Guidelines on
  information security controls for the use of cloud computing services based on ISO/IEC 27002
* ISO/IEC 27018, Code of Practice for Data Protection Controls for Public Cloud Computing Services
* ISO/IEC 1st WD 27036-4, Information technology – Security techniques – Information security for supplier relationships
  – Part 4: Guidelines for security of cloud services

Security Policy Management:
* ATIS-02000008, Trusted Information Exchange (TIE)
* FIPS 199, Standards for Security Categorization of Federal Information and Information Systems
* FIPS 200, Minimum Security Requirements for Federal Information and Information Systems
* ISO/IEC 27002, Code of practice for information security management
* eXtensible, Access Control Markup Language (XACML)

Availability:
* ATIS-02000009, Cloud Services Lifecycle Checklist
* ISO/PAS 22399:2007, Societal security - Guideline for incident preparedness and operational continuity management

### Service Interoperability

* Cloud Infrastructure Management Interface DMTF (CIMI)
* IEEE P2301, Draft Guide for Cloud Portability and Interoperability Profiles (CPIP)
* IEEE P2302, Draft Standard for Intercloud Interoperability and Federation (SIIF)
* Y .3520, Cloud computing framework for end to end resource management.
* Cloud Application Management Platform OASIS (CAMP)
* Open Cloud Computing Interface (OCCI)
* Data Format Description Language (DFDL)
* Topology and Orchestration Specification or Cloud Applications (TOSCA), Version 1.0 Committee Specification Draft 06 /
  Public Review Draft 01
* Cloud Data Management Interface (CDMI) [Also approved as ISO/IEC 17826:2012, Information technology – Cloud Data] 
  Management Interface (CDMI)

### Cloud-specific Portability

* Cloud Data Management Interface (CDMI)
* Open Virtualization Format (OVF), OVF 1.0 [Also approved as INCITS 469-2010 & ISO/IEC 17203: 2011]
* Open Virtualization Format (OVF), OVF 2.0
* IEEE P2301, Draft Guide for Cloud Portability and Interoperability Profiles (CPIP)
* Topology and Orchestration Specification for Cloud Applications (TOSCA), Version 1.0, Committee Specification Draft 06
  / Public Review Draft 01

### Performance

Performance standards are needed for cloud service agreements and for cloud service monitoring.

* Topology and Orchestration Specification for Cloud Applications (TOSCA), Version 1.0, Committee Specification Draft
  06 / Public Review Draft 01
* GB917, SLA Management Handbook, Release 3.1
* GB963, Cloud SLA Application Note, Version 1.2
* TR178, Enabling End-to-End Cloud SLA Management, Version 0.4
* TR194, Multi-Cloud Service Management Accelerator Pack - Introduction, Release 1.0
* TR195, Multi-Cloud Service Management Pack - Business Guide, Release 1.0
* TR196, Multi-Cloud Service Management Pack - Technical Guide, Release 1.0
* TR197, Multi-Cloud Service Management Pack – SLA Business Blueprint
* TR198, Multi-Cloud Service Management Pack – Developer Primer

## Standardization Gaps

* use case: creating, accessing, updating, deleting data objects in cloud systems
* use case: moving VMs, virtual appliances, services, and appliances
* use case: selecting the best IaaS cloud vendor, public or private
* use case: portable tools for monitoring and managing cloud systems
* use case: moving data between cloud systems
* use case: single sign-on access to multiple cloud systems
* use case: orchestrated processes across cloud systems and enterprise systems
* use case: discovering cloud resources
* use case: evaluating SLAs and penalties
* use case: auditing cloud systems
* end-to-end: cloud resource management use case
