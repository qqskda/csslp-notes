# General Security Concepts

## Concepts

### Security Basics

📝 Determining and applying the appropriate balance of confidentiality, integrity, and availability (CIA)

Although different, they are not necessarily contradictory - but they all require resources (money) and so the balance should be determined early on in the design process

#### Confidentiality

- **Prevent disclosure of information to unauthorized parties**
- Numerous methods for keeping data confidential: e.g. access controls, encryption
- **Access Controls**: Preferred for data in use and at rest
- **Encryption**: Data at rest and in transit

#### Integrity

- **Protect data from unauthorized alteration**
- e.g. Read-only, Read-and-write, write-only, delete access, etc
- Integrity contributes to a system's **stability** and **reliability** as well as the **authenticity** of data
  - 안정성, 신뢰성, 진실성 (정확성)

#### Availability

- Availability needed is determined by criticality of data and purpose in the overall system
  - 데이터의 중요성과 전체 시스템의 목적에 의해 정해짐

#### Authentication

- **Determining the _identity_ of a user. A user is authenticated before their authorization can be determined.**
  - 가장 첫번째로 우리가 해야할것은 해당 유저가 정말 그 유저가 맞는지를 확인하는것

- To verify identity, a user can provide:
  - Something you know - e.g. username/password (not very reliable)
  - Something you have - e.g. token
  - Something about you (something you are) e.g. biometrics
    - ❗ Requires extra hardware, lacks specificity

- New categories
  - what users do (dynamic biometrics such as typing patterns, gait)
  - where a user is (physical location)

- ATMs use combination of something you know (PIN) and something you have (card) so if the card is lost, someone cannot authenticate as you

#### Authorization

- **Applies predetermined access levels to the user**
  - 해당 유저에게 미리 정해진 access level를 반영하는것

1. Three elements are used (누가, 무엇을, 어떻게 할수 있는지를 정하는것)
   1. Requestor (subject) - already known due to authentication system
   2. Object
      1. file, program, data, other resource
   3. Type/level of access to be granted
      1. Read, write, create, delete, right to grant access rights to other objects

#### Accounting (Auditing)

- **Accounting is a means of measuring activity, auditing is the verification of what actual happened and allows management to observe in a nonpartisan (객관적) manner**
  - Accounting: 활동 측량, Auditing: 활동 확인
- Accounting can be done in IT systems by logging crucial activity as it occurs
- Accounting is needed when activity of specific data elements is crucial enough that it may be audited at a later date and time

- Security level auditing can be performed at several levels:

  - analysis of logging function
  - verification of existence and operation of specific controls
  - etc

- Auditing takes resources to create, store, and review. Typically defaulted to minimal level so system operator must determine correct level based on system criticality.
  - Auditing은 하려면 자원이 필요함. 그래서 보통 auditing 을 할 수 있는 필요한 최소한으로만 설정함.
- **System criticality** is determined by information criticality associated with information manipulated/stored with the system

#### Non-repudiation (부인방지 - 어느 행위를 하지 않았다고 부인하는것을 방지하는것)

- **Preventing a subject from denying a previous action with an object**
- When authentication, authorization, and auditing are properly configured, non-repudiation is ensured
  - 신원 확인, 허가, 감사가 제대로 이루어지면 부인방지가 불가능함 (누가 뭘 했는지 적어뒀으니까)
- **Security requirements must specify the subjects, objects, and events for which non-repudiation is desired**

### System Tenets (교의/주의/원리)

#### Session Management

- **Design and implementation of controls to ensure that communication channels are secured from unauthorized access and disruption**
- TCP (Transmission Control Protocol)
  - sequential numbering of packets and retransmission for missing packets
  - Prevents unauthorized packets and session hijacking
  - Has overhead
- UDP (User Datagram Protocol)
  - connection-less/session-less

#### Exception Management

- All exceptions must be detected and handled
- System should not fail in an insecure state
- Exception should not be leaked

#### Configuration Management

- Configuration should be protected from unauthorized changes
- e.g. separation of duties between production/non-prod personnel

### Secure Design Tenets

#### Good Enough Security

- Don't spend $10,000 to protect a $20 bill
- Trade-offs exist between security and other aspects

#### Least Privilege

- If a subject may require different levels of security for different tasks, better to switch security levels with specific tasks than run all the time at higher privilege

#### Separation of Duties

- No single individual can abuse the system

#### Defense in Depth

- i.e. layered security/defense and diversity defense
- Multiple, overlapping defenses
- No system is 100% secure - **true goal of security is to make cost of compromising greater in time/effort/resources than it is worth**
- Diversity of defense - layers should be dissimilar in nature

#### Fail-safe

- **When a system experiences a failure, it should fail to a safe state**
- Example: explicit deny
- CIA need to be appropriately maintained - availability causes the greatest design difficulties

#### Economy of Mechanism

- Higher complexity generally results in less security due to lack of understanding and more attack vectors
- Root cause analysis, especially for potential security issues, is much more difficult in complex systems
- **Rule of thumb**: eliminate all nonessential services and protocols
- 메커니즘이 복잡할 수 록 오히려 관리를 못해서 허점이 더 많음. 따라서 필요없는 서비스와 프로토콜을 없애는게 더 이득임.

#### Complete Mediation (중재)

- **Authorization is never circumvented, even with repeated access**
- Example: security kernel
- 같은 작업의 반복 (커널에서 프로그램 설치시 항상 admin account 비번 물어보는거)일 지라도 authorization 에 예외를 두지 않는다.

#### Open Design

- Don't rely on security by obscurity (모호함); 막연하게 믿지 말라는거
- Example: modern cryptography relies on the secrecy of the key, not secrecy of the algorithm
  - 정확하게 뭘 알고 하라는듯. 그리고 알려진 보안 체계 (여러 사람에게 리뷰를 받은)를 사용하는게 안전함.

#### Least Common Mechanism

- **Prevent inadvertent (부주의한, 우연히 무심코) sharing of information by using separate processes when possible**

#### Psychological Acceptability

- Users will try to get around security if it is seen as an obstacle
  - 쉬우면 받아들이고 어려우면 꼼수 생각해냄 유저들은

#### Weakest Link

- Adding to the security of a system is most effective when applied to the weakest link

#### Leveraging Existing Components

- 이미 사용자들이 익숙한 것들로 계속 사용하는거 (개발자 등등). 잘 아는 것들이니 사용 효율도 높고 보안도 높음.
- 대신 해당 시스템이 뚫리면 큰일나기도 하고, 최신화 프로그램을 따라가지 못해 개발이 중단되는 사태도 가능함 (옛날 DB 프로그램 사용한다던가)
- Pros: increase efficiency and security 
- Cons: monoculture (단일) environment (failures have a larger footprint)

#### Single Point of Failure

No one single piece should be able to cause the whole system to fail

// Aug 1 2022
## Security Models

- Three key elements: people, processes, and technology (사람, 절차, 기술)
- Controls using 2-3 elements are more effective

### Access Control Models

#### ACL - access control list

#### MAC - mandatory access control

- rarely used
- originated in military
- **restrict based on information sensitivity and clearance to access that information**
- system designers have to determine object/subject relationships before they can be used

#### DAC - discretionary access control

- most common
- originated in military
- **restrict based on identity of subjects/groups they belong to**
- If a subject has permission, it is capable of passing that permission onto any other subject
- ACLs are the most common mechanism used to implement this control
- **Strength**: simplicity
- **Weakness**: security is optional, owner has to define access for potentially a plethora of objects

#### RBAC - role-based access control

pretty common for active directory

#### RBAC - rule-based access control

- much less common than role-based
- Use ACLs that have rules baked in such as only allow access during a certain time-of-day

#### Access control matrix model

- strength: simplicity
- weakness: difficult to implement due to no constraints, doesn't scale well

#### ABAC - attribute-based access control

- Example: doctor getting one set of access for a specific patient vs a different patient
- Represented via eXtensible Access Control Markup Language (XACML)
  - also works for policy-based access control

#### Bell-LaPadula Confidentiality Model

1. Two principles
   1. Simple Security Rule - in order to see something, you have to be authorized
      1. Used to preserve confidentiality - e.g. subject with medium clearance can't ready information with high sensitivity, only medium sensitivity
      2. No-read-up
   2. \* property (star property)
      1. No-write-down
      2. Subjects can only write to an object if the object has equal or higher classification - e.g. medium clearance can only write to medium sensitivity and above

#### Take-Grant Model

- Uses graph theory based on mathematical representation of controls
- Can be used to definitively determine rights
- Not typically used to implement access control but rather to analyze implementations

### Multilevel Security Model

- **Separate groups have labels, groups act as containers, can be hierarchical**

### Integrity Models

- Depending on type of information, can be just as important or more important than confidentiality. e.g. stock prices (public but integrity is crucial)

#### Biba Integrity Model

- Preserves information integrity
- Integrity levels separate permissions
- Low water mark policy, i.e. no-write-up rule
  - lower integrity subjects can't write up to higher integrity subjects
- Integrity level of a subject is lowered if it acts on a subject with lower integrity

#### Clark-Wilson security model

- Uses transactions
- Two levels:
  - Constrained data items (CDI)
    - Subject to integrity controls
- Unconstrained data items (UDI)
- Two types of processes:
  - Integrity verification processes (IVPs)
    - Ensure CDI data meets constraints
  - Transformation processes (TPs)
    - Change state of data from one to another
    - Data can only be changed by trusted TPs, not users

Example:

- A bank account balance is a CDI since integrity is important
- TP is the only way changes can be made
- IVP ensures balance is correct

### Information Flow Models

#### Brewer-Nash Model (Chinese Wall)

- Technology employed to prevent access
- People trained not to compromise information
- Policies/processes put in place to ensure technology/people are properly used

#### Data Flow Diagrams (DFDs)

- Main security issue is protecting information when stored, in transit, and being processed
- Multiple levels - Level 0 (high level), level 1, level 2 (lowest level)

#### Use Case Model

- Functional perspective - how the system uses data

- Use cases for normal and abnormal use
  - **Very important to security to understand use cases and misuse cases**

#### Assurance Models

- **Software assurance - level of confidence that software is free from intentional and accidental vulnerabilities, software functions as intended**

#### Operational model of security

Three methods of managing security:

1. prevention - access control, firewall, encryption
2. detection - audit logs, intrusion detection, honeypots
3. response - backups, incident response teams, forensics

#### NIST CSF

Standards, guidelines, best practices

5 main categories:

1. Identify
2. Protect
3. Detect
4. Respond
5. Recover

## Adversaries

Includes mother nature :)

### Adversary Type

- **Based on skill level**

1. Script Kiddie - 80-85% of adversaries
2. Hacker - explorer - 15-20% **key adversary due to skill/motivation**
   1. Cracker - hacker with malicious intent
3. Elite - 1-3%
   1. completely underground

### Adversary Groups

#### Skill and capability

1. Unstructured threat - little or no resources, no specific motivation, typically only an annoyance
2. Structured threat - specific mission, time and resources
3. Highly structured threat - organized crime, crimeware
4. Nation-state threat
   1. Advanced persistent threat (APT) - multiple methods to penetrate and then live undetected
5. Insider vs outsider

### Threat Landscape Shift

- Around 2005 - criminalization of cyberspace allowing monetization
- Market for exploits
