+++
date = '2025-02-11T23:07:12+03:30'
title = 'DNS Protocol and Attacks'
+++

# DNS Protocol & Attacks

## Introduction

#### What is DNS?

> DNS Stands for Domain Name System

- **DNS (Domain Name System):**
  
  - Translates human-friendly domain names (e.g., `www.amazon.com`, `www.netflix.com`) into numeric IP addresses that computers use to identify each other on the Internet.

- **The Human vs. Computer Paradigm:**
  
  - Humans can easily remember domain names, while computers rely on numeric IP addresses (e.g., IPv4 like `51.23.8.9` or IPv6 like `2400:CB00:2048:1::C629:D782`).

- **DNS as the Internet’s Phonebook:**
  
  - Functions similarly to a phonebook by allowing users to look up a domain name and retrieve the corresponding IP address.
  - Eliminates the need for humans to memorize or manually input complex IP addresses.

- **Critical Role in Internet Functionality:**
  
  - Enables everyday tasks such as online shopping, banking, and streaming by seamlessly connecting domain names to the correct servers.
  - Without DNS, the usability of the Internet as we know it would be significantly diminished.

- **Beyond Basic Name Resolution:**
  
  - While the basic function of DNS is to translate names to IP addresses, its underlying architecture is more sophisticated and versatile.
  - Further course content will explore these complexities in greater detail.

#### The main Function if DNS

- **Three Main Functions of DNS:**
  
  - **Name Resolution:**
    - Translates domain names into IP addresses.
    - This is the core function of DNS.
  - **Namespace:**
    - Defines how domain names are structured.
    - Determines what makes a name valid, including the format and allowed characters/symbols.
    - Explains how names are interpreted.
  - **Name Registration:**
    - Involves the process of registering a domain.
    - Ensures the uniqueness of domain names.
    - Details the role of registration authorities in the name assignment process.

- **Complexity and In-Depth Study:**
  
  - Each of these areas (name resolution, namespace, and name registration) is broad and detailed.
  - The course is structured to dedicate a section to each function to explore them fully, starting with namespace.

## Name Space

#### Domain Name Format

- **Introduction:**
  
  - Covers the breakdown of a typical domain name into individual components.
  - Emphasizes that this lecture lays the foundational knowledge for understanding DNS namespaces.
  - Recommendation for beginners: watch the video more than once and take detailed notes.

- **Domain Name Interpretation Direction:**
  
  - Although we type domain names from left to right, DNS interprets them from **right to left**.

- **Components of a Domain Name (from Right to Left):**
  
  - **Root (Special Dot):**
    - Represented by a unique, dominant dot at the far right.
    - This dot is distinct (often colored differently) and serves as the ultimate terminator of a domain name.
  - **Top-Level Domain (TLD):**
    - Follows immediately after the root.
    - Example given: `.com` (others include `.net`, `.org`, `.io`, etc.).
    - Combined with the second-level domain, it forms the **zone apex** (or naked/apex domain).
  - **Second-Level Domain (SLD):**
    - In the example, this is `example`.
    - Along with the TLD, it makes up the main, recognizable part of the domain.
  - **Third-Level Domain:**
    - Commonly used as `www`, but it’s simply a naming convention and can be replaced by any arbitrary string.
  - **Labels:**
    - Each part (root, TLD, SLD, etc.) is known as a **label**.
    - Each label is a subdomain of its parent domain.
    - The entire sequence of labels from the root up forms the **Fully Qualified Domain Name (FQDN)**, which is the absolute reference to a domain.

- **Domain Name vs. URL:**
  
  - **Domain Name:** Only the name component (e.g., `www.example.com`).
  - **URL:** Includes additional components such as the protocol (e.g., `https://`) and path (e.g., `/learning`).

- **Partially Qualified Domain Name (PQDN):**
  
  - A domain name that includes the hostname but does not extend all the way to the root.

- **Syntax Rules for Domain Names:**
  
  - **Label Length:** Each label can be up to 63 characters long.
  - **Allowed Characters:** Letters (a–z, A–Z), digits (0–9), and hyphens.
    - This is referred to as the **LDH rule**.
    - Labels cannot begin or end with a hyphen.
  - **TLD Restrictions:** Top-level domains should not be entirely numeric.
  - **Subdomains:** There is no maximum limit on the number of subdomains.
  - **Overall Length:** A complete domain name can be up to 255 characters, including dots.

- **Conclusion:**
  
  - Recap of the domain name components and syntax.
  - Transition note: This lecture sets the stage for deeper discussions in later parts of the course.

#### The DNS Tree

- **Introduction:**
  
  - Recap of domain name composition.
  - Transition into understanding the context in which domain names exist.

- **DNS vs. Phonebook Analogy:**
  
  - **Similarities:**
    - Both map names to numbers (e.g., DNS maps domain names to IP addresses; a phonebook maps names to telephone numbers).
  - **Differences in Structure:**
    - A phonebook is a single, centralized authority covering a specific geographic region.
    - A central database approach (flat name architecture) is used in a phonebook, which doesn’t scale well for the entire Internet.

- **Challenges with Flat Name Architecture:**
  
  - **Administrative Overhead:**
    - Managing every possible domain name in a central database would be extremely demanding.
  - **Scalability Issues:**
    - Flat systems do not scale well to handle hundreds of thousands (or millions) of devices.
  - **Uniqueness Guarantee:**
    - It is extremely difficult to ensure that every domain name is unique across a flat namespace.

- **Adoption of Hierarchical Name Architecture:**
  
  - **Rationale:**
    - To overcome the limitations of a flat architecture, DNS uses a multi-level hierarchical structure.
  - **Structure:**
    - The Internet is organized as a globally distributed collection of databases that form a tree-like structure.
    - Each domain name represents a path in this tree.
  - **Decentralized Administration:**
    - Authority is delegated to various organizations.
    - Each organization manages its own domain data and can further subdivide into subdomains.
    - This delegation supports scalability and simplifies management.

- **Benefits of the Hierarchical Model:**
  
  - **Decentralized Administration:**
    - No single entity manages the entire namespace.
  - **Management Flexibility:**
    - Organizations can manage and delegate subdomains, allowing the namespace to grow organically with the Internet.
  - **Uniqueness:**
    - The hierarchical structure helps guarantee that every domain name is unique across the global Internet.

- **DNS Infrastructure Overview:**
  
  - **Components:**
    - **Root Name Servers:** Sit at the top of the hierarchy.
    - **Top-Level Domain (TLD) Name Servers:** Follow the root servers.
    - **Authoritative Name Servers:** Provide the final mapping to IP addresses.
  - **Next Steps:**
    - The next lecture will focus on studying the root name servers and their critical role in the DNS namespace.

#### Root Servers

- **Introduction to Root Servers:**
  
  - Recap of DNS’s role in translating domain names into IP addresses (name resolution).
  - Introduction to the concept of "roots" within the DNS hierarchy.

- **Role and Function of Root Servers:**
  
  - **First Point of Contact:**  
    - Root servers are the first component in the DNS tree that receive a DNS query.
  - **Referral Process:**  
    - Upon receiving a query, a root server provides a referral to the appropriate top-level domain (TLD) name server based on the domain extension.
    - Example: For `www.yahoo.com`, the root server passes the query to a TLD server corresponding to `.com`.

- **Understanding the Query Process:**
  
  - The conversion of a domain name to an IP address (name resolution) starts with a query that is first directed to a root server.
  - Additional systems and background technologies work before a query reaches a root server, as indicated by visual cues (like square brackets with dots) in the presentation slides.

- **Key Details About Root Servers:**
  
  - **Number and Naming:**  
    - There are 13 root name servers, each identified by letters A through M.
  - **Further Information:**  
    - Detailed data about these servers—including operators, physical locations, IP and IPv6 addresses, and related autonomous system numbers (associated with the BGP protocol)—is available at [root-service.org](https://root-service.org).
  - **Infrastructure Scale:**  
    - Although there are 13 designated servers, there are multiple physical copies (over 130 locations worldwide) to manage high traffic loads.
    - As of February 20, 2019, there were 938 operational root server instances globally.

- **Conclusion:**
  
  - Root servers play a critical role in the DNS resolution process.
  - A deeper understanding of root servers and their role will be built upon in later discussions on name resolution.

#### TLD Servers

- **Role in DNS Resolution:**
  
  - **Transition from Root Servers:**  
    - After a DNS query reaches a root server and receives a referral, the query is passed to a TLD nameserver.
  - **Primary Function:**  
    - The TLD nameserver’s job is to provide its own referral pointing to an authoritative nameserver that has authority over the requested domain (e.g., Yahoo).

- **Hierarchical Architecture:**
  
  - **Distributed Databases:**  
    - Unlike a flat architecture with a single central database, DNS uses a hierarchical system where each branch holds only part of the necessary information.
  - **Step-by-Step Resolution:**  
    - Each level in the DNS hierarchy (root, TLD, and authoritative) contributes a piece of the puzzle needed to fully resolve a domain name.

- **Categories of Top-Level Domains:**
  
  - **Generic Top-Level Domains (gTLDs):**
    - Reflect the type of organization or industry (e.g., `.com`, `.edu`).
    - Example: Government agencies typically use `.gov`, and universities use `.edu`.
    - The original gTLDs included domains like `.arpa`, `.com`, and `.net`; newer ones like `.aero` and `.pro` have also been added.
  - **Country Code Top-Level Domains (ccTLDs):**
    - Allow countries to manage their own namespace and cater to local languages and needs.
    - Examples include Japan’s `.jp`, Greece’s `.gr`, Italy’s `.it`, and Poland’s `.pl`.
    - Countries may also use organizational subdomains within their ccTLDs (e.g., the UK uses `.co.uk` for companies, and Australia uses `.com.au`).

- **Additional TLD Categories:**
  
  - Other specialized TLD categories exist beyond gTLDs and ccTLDs; however, these are outside the scope of this course.
  - For a complete list of TLDs, refer to the IANA website at:  
    `https://www.iana.org/domains/root/db`

- **Conclusion and Next Steps:**
  
  - The TLD nameserver plays a crucial role by passing back a referral to the authoritative nameserver for the requested domain.
  - The next lecture will continue the journey by explaining how the query reaches and is handled by the authoritative nameservers.

#### Authoritative Name Servers

- **Introduction to Authoritative Name Service:**
  
  - Marks the final component of the DNS namespace section.
  - Focuses on the role of the authoritative name server in completing the DNS resolution process.

- **Understanding Authority in DNS:**
  
  - **Definition of Authority:**
    - In DNS, a *domain* represents a sphere of influence governed by an entity responsible for managing that portion of the namespace.
    - Authority implies responsibility for providing accurate DNS data (e.g., IP addresses) for that segment.
  - **Analogies:**
    - Like a medieval lord governing a territory or an expert being the leading authority in a field, an entity in DNS manages a specific domain.
  - **Hierarchical Nature:**
    - The DNS namespace is divided into segments, each managed by a designated authority.
    - A single authority can manage multiple levels of the hierarchy (e.g., ICANN manages both the root and TLD segments).

- **Role of the Authoritative Name Server:**
  
  - **DNS Resolution Process:**
    - Initial queries are handled by root servers and then TLD (Top-Level Domain) servers.
    - Both the root and TLD servers provide referrals because they are not authoritative for specific domains (e.g., www.youtube.com).
  - **Final Step:**
    - The authoritative name server holds the definitive DNS records for a domain.
    - It completes the resolution process by returning the final answer (the IP address) for the requested domain (e.g., www.yahoo.com).
  - **No Further Referrals:**
    - Unlike previous steps, once the query reaches the authoritative server, there is no further referral—just the final response.

- **Delegation and Management within the DNS Hierarchy:**
  
  - Organizations (like ICANN) can manage broad segments (e.g., the root or an entire top-level domain).
  - Domain owners can delegate authority over subdomains to other organizations.
    - *Example:* As the owner of *securitycharms.com*, you might delegate management of a subdomain (e.g., *sub.securitycharms.com*) to another entity.

- **Course Recap and Next Steps:**
  
  - **Topics Covered in the Namespace Section:**
    - Definition of DNS and its primary functions.
    - The DNS tree structure and domain name syntax.
    - The roles of root servers, TLD servers, and authoritative name servers.
  - **Progress Acknowledgment:**
    - With this lecture, you’ve reached an intermediate level of understanding.
  - **Looking Ahead:**
    - The course will continue with a focus on the name resolution process in greater detail.
