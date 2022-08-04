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
  - 어느 자원에 접근할때 보안 레이블과 보안 허가증을 참고하여 통제한다 (security clearance 같은거)
- 매우 엄격한 통제 모델이라 보안이 좋고, 중앙 집중식 관리 형태라 관리가 용이하면서도 힘들다.
- 다만 모든 접근과 정책에 대해 확인해야 하므로 성능저하가 발생하여 상업 분야에서 사용되기 어렵다.

#### DAC - discretionary access control

- most common
- originated in military
- **restrict based on identity of subjects/groups they belong to**
- If a subject has permission, it is capable of passing that permission onto any other subject
  - 즉 어느 사람이 어느 자원에 대해 권한을 가지고 있다면, 다른 사람에게 해당 자원 접근을 허용/제한할 수 있다 (개인/그룹 정책)
- ACLs are the most common mechanism used to implement this control
- **Strength**: simplicity
- **Weakness**: security is optional, owner has to define access for potentially a plethora of objects
  - 소유자가 임의적 접근 허용을 해주어서 보안이 조금 떨어지며, 신분이 도용당할 경우 답도 없다.

#### RBAC - role-based access control

pretty common for active directory
- much less common than role-based
- Use ACLs that have rules baked in such as only allow access during a certain time-of-day
- 신분이 아닌 역할에 따른 접근 권한 부여이므로 역할을 바꿈에 따라 유연하게 접근 권한을 바꿀수 있다.

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
2. 즉 중간 직책의 관리자는 중간및 하위 정보를 읽을수 있으나, 중간및 상위 보안의 정보를 작성할 수 밖에 없음.
   1. 이렇게 하면 중간 직책 관리자는 필요한 정보 중간/하위를 얻을수 있고.
   2. 하위 정보를 작성할 수 없음으로 상위 정보가 하위로 샐 걱정을 하지 않아도 됨.

위키:
보안 정책은 정보가 높은 레벨에서 낮은 레벨로 흐르는 것을 방지
(No Read Up): 낮은 등급의 주체는 높은 등급의 객체를 읽을 수 없음
(No Write Down): 높은 등급의 주체는 낮음 등급의 객체를 수정할 수 없음
한계점: Blind Write(무결성 파괴)

#### Take-Grant Model

- Uses graph theory based on mathematical representation of controls
- Can be used to definitively determine rights
- Not typically used to implement access control but rather to analyze implementations
- 관계도 그려서 (권한에 따른) 보안 허점 분석하는 모델

### Multilevel Security Model

- **Separate groups have labels, groups act as containers, can be hierarchical**
  - 각기 다른 그룹들은 레이블을 가지고 있고 (서버코어, 페이먼트...), 컨테이너에 속하고 (Dev Team), 계층적일수 있다 (CTO-DevTeam...)

### Integrity Models

- Depending on type of information, can be just as important or more important than confidentiality. e.g. stock prices (public but integrity is crucial)
  - 정보의 종류에 따라 무엇이 중요한지는 다를수 있음. 정보의 정확성이 중요하면 기밀성은 조금 떨어져도 괜찮 (주식 정보등)

인가되지 않은 사용자에 의해 데이터가 수정되는 것을 통제
인가된 사용자라 할지라도 권한이 없는 데이터를 수정하는 것을 통제
데이터는 내/외부적으로 일관성을 유지
무결성을 위한 규칙: 주체 → 프로그램 → 객체

#### Biba Integrity Model

- Preserves information integrity
- Integrity levels separate permissions
- Low water mark policy, i.e. no-write-up rule
  - lower integrity subjects can't write up to higher integrity subjects
- Integrity level of a subject is lowered if it acts on a subject with lower integrity

BLP의 단점을 보완한 무결성을 보장하는 최초의 모델
무결성의 3가지 목표 중 비인가자의 데이터 수정 방지 가능
비바 무결성 모델의 속성 - 밑에서 등급은 무결성 등급을 말함
(No Read Down): 높은 등급의 주체는 낮은 등급의 객체를 읽을 수 없음
(No Write Up): 낮은 등급의 주체는 상위 등급의 객체를 수정할 수 없음

무결성과 기밀성의 차이를 생각해보면 왜 방향이 반대인지 이해 가능함.

#### Clark-Wilson security model

- Uses transactions
- Two levels:
  - Constrained data items (CDI) **(통장잔고)**
    - Subject to integrity controls
  - Unconstrained data items (UDI)
- Two types of processes:
  - Integrity verification processes (IVPs) **(통장 잔고 무결성)**
    - Ensure CDI data meets constraints
  - Transformation processes (TPs) **(통장 잔고 변동)**
    - Change state of data from one to another
    - Data can only be changed by trusted TPs, not users
    - 아까 위에 적힌 무결성을 위한 규칙: 프로그램이 객체를 수정한다.

Example:

- A bank account balance is a CDI since integrity is important
- TP is the only way changes can be made
- IVP ensures balance is correct

무결성 중심의 상업용 모델로 설계된 모델
상용 응용 보안 요구 사항을 다루고 있음
금융·회계 데이터는 자산에 대한 정보를 취급하고 있어 변조 방지가 더욱 중요
예측 가능하고 완전하게 처리되는 자료처리 정책이 필요

### Information Flow Models

#### Brewer-Nash Model (Chinese Wall)

- Technology employed to prevent access
- People trained not to compromise information
- Policies/processes put in place to ensure technology/people are properly used
  
충돌을 야기하는 어떠한 정보의 흐름도 차단해야 한다는 모델로 이익 충돌 회피를 위한 모델
직무 분리를 접근 통제에 반영한 개념이 적용
금융 서비스 제공 회사가 이해 충돌의 발생을 막기 위해 설계된 내부 규칙
적용 영역: 투자, 금융, 파이낸셜, 로펌, 광고 분야

#### Data Flow Diagrams (DFDs)

- Main security issue is protecting information when stored, in transit, and being processed
- Multiple levels - Level 0 (high level), level 1, level 2 (lowest level)
- 걍 그냥 말 그대로 데이터 흐름 다이어그램 (무엇이 어디서 어디로 가고 어떻게 processed 되는지)

#### Use Case Model

- Functional perspective - how the system uses data

- Use cases for normal and abnormal use
  - **Very important to security to understand use cases and misuse cases**
  - 당연히 알맞게 사용될때, 그리고 비정상적으로 사용할때 다 고려해야함

#### Assurance Models

- **Software assurance - level of confidence that software is free from intentional and accidental vulnerabilities, software functions as intended**
  - 고의적/우연한 취약점에서 부터 얼마나 자유롭고 의도한 대로 작동할지에 대한 confidence level; 

#### Operational model of security

Three methods of managing security:

1. prevention - access control, firewall, encryption
2. detection - audit logs, intrusion detection, honeypots
3. response - backups, incident response teams, forensics
// Aug 1 2022
#### NIST CSF (National Institute of Standards and Technology - Cybersecurity Frame)

Standards, guidelines, best practices

5 main categories:

1. Identify - 신원 
2. Protect  - 보호
3. Detect   - 감지
4. Respond  - 반응
5. Recover  - 회복

## Adversaries (적수 - 적대국...)

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
   1. 딱히 동기없이 그냥 귀찮게 하는 위협정도
2. Structured threat - specific mission, time and resources
   1. 특정한 임무, 그리고 시간과 자원을 들여서 하는 위협
3. Highly structured threat - organized crime, crimeware
   1. 범죄 레벨
4. Nation-state threat
   1. Advanced persistent threat (APT) - multiple methods to penetrate and then live undetected
5. Insider vs outsider

### Threat Landscape Shift (위협 양상의 변화)

- Around 2005 - criminalization of cyberspace allowing monetization
- Market for exploits
