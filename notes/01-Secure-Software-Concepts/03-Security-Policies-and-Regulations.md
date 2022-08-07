# Security Policies and Regulations

- **All hazards**: senior management is responsible for security, compliance, all exercises in risk management

## FISMA

- **Federal Information Security Management Act of 2002**
- 📝 Primary governing law for federal computer systems (정부 컴퓨터 시스템 관련 법)

- Requires each federal agency to implement a security program
- NIST (National Institute of Standards and Technology) developed guidelines
- Risk Management Framework (RMF) was published by NIST
  - Initial framework included: (재고화, 카테고리 관리, 각 시스템에 관한 측정및 대책, 그리고 트레이닝)
    - Inventory of systems (시스템의 재고화 - know what you have)
    - Categorize information and systems according to risk level (위험 레벨에 따른 카테고리화)
    - security controls 
    - Certification/accreditation of systems (risk assessment and security plans)
    - Training
- Information Security Automation Program
- Security Content Automation Protocol (SCAP)

NIST six steps for a RMF:

1. Categorize systems - 카테고리화
2. Select security controls - 선택
3. Implement controls - 설치
4. Assess Controls - 권한 확인
5. Authorize information systems - 허가
6. Monitor controls - 모니터링

## Sarbanes-Oxley (2002)

- financial accounting information systems must have control over integrity (금전 관련은 역시 무결성이 제일 중요)

## Gramm-Leach-Bliley Act / Financial Modernization Act of 1999 (GLBA)

- Protect PFI (personal financial information)
  - act specifies rules for collection, processing, storage, and disposal of PFI
  - 유럽의 PII 랑 비슷한거
Primary rules:

1. Financial Privacy Rule - collection and disclosure of PFI
2. Safeguards Rule - applies to financial institutions - covers design, implementation, and maintenance of safeguards to protect PFI
3. Pretexting Protections Rule - address pretexting (falsely pretending) to obtain PFI
   1. 즉 누군가인척 하면서 정보를 얻은 행위 혹은 하려던 것은 불법

## HIPAA and HITECH

- HIPAA - (Healthcare Insurance Portability and Accountability Act)
  - Protect PHI (personal health information)
- HITECH - (Health Information Technology for Economic and Clinical Health Act)
  - enhance privacy of electronic PHI records

## Payment Card Industry (PCI)

Industry group established to secure cardholder data; 카드 소유자 데이터 보호 하기 위한 그룹

### Data Security Standard (PCI DSS)

Industry group members that accept and process bank cards are required to protect cardholder data; 카드 결제를 사용하는 곳은 해당 데이터를 보호해야만 함

### Payment Application Data Security Standard (PA DSS)

Standard to validated that a payment application is compliant with PCI DSS - Private Card Info Data Security standard

### PIN Transaction Security (PTS)

Applies to PIN Entry Devices (PEDs)

## Legal Issues

### Intellectual Property

1. Patents - 특허
   1. Exclusive right for a specified time
      1. 특정 시간동안 독점
   2. protect rights in exchange for disclosure of invention
      1. 발명 한것을 공개해주는것을 인정해서 보호 해주는거
   3. Varies by country but in the US, invention must be new, useful, and non-obvious
   4. Prevent others from using invention
   5. Patent must be applied for prior to disclosure
      1. 공개전에 특허를 신청해야함
   6. challenging and expensive
2. Copyrights - 저작권
   1. Protection of an idea or information for a specified time
      1. 아이디어나 정보를 보호해주는것
   2. right to be credited, who may adapt, who may perform, who may financially benefit, etc
      1. 누가 어떻게 사용할지에 대해서 권한을 주는것 (즉 저작권자의 허락을 맡아야 사용할 수 있다)
   3. governed internationally by Berne Convention
   4. straightforward and affordable
3. Trademarks - 등록 상표
   1. recognizable quality of product/firm
      1. 제품 혹은 회사의 인식 가능한것; 로고같은 브랜드 관련
   2. used to build brand association
   3. can be common-law or registered - registered provides more legal protection and recovery
   4. managed internationally through World Intellectual Property Organization
4. Trade Secrets - 영업 비밀
   1. best time-based protection
      1. 가능하면 평생 비밀도 가능함
   2. protected by many laws as long as company makes a reasonable attempt to keep it secret
      1. 비밀을 지키기 위해 노력했으면 법들에 의해 보호 받음; 즉 누군가 고의로 침입해서 훔쳐가는것등을 보호
   3. if secret is independently discovered (e.g. recipe), then secret holder has no recourse
   4. US Digital Millenium Copyright Act prohibits reverse-engineering of security safeguards
5. Warranty - 워런티
   1. hardware often has a warranty to perform at the specified level
   2. software does not and is generally sold as is
      1. 보통 소프트웨어는 워런티가 없고 그냥 그대로 팔림; ㅋㅋㅋㅋㅋㅋ

## Privacy

- To obtain certain goods, users must consent to share certain information
  - 어느 물품을 구매하기 위해서는 사용자는 어느 일정한 정보를 공유해야함
  - 아이디, 비밀번호, 배달 주소, 핸드폰 번호, 이름 등등
- One main issue with privacy is data disposition; 데이터 처리
- 📝 founded on notice, choice, and security

### Privacy Policy

Internal privacy policy details the firm's responsibilities to protect information

External privacy policy, or privacy disclosure statement, informs customers how data is protected, used, and disposed of

In financial sector, Gramm-Leach-Bliley Act mandates firms clearly state how information is shared

### PII

### PHI (Personal Health Information / Protected Health Information)

Highly valued by cyber criminals

### Breach notifications (털린거 어떻게 알려야 하는지)

- Incident response (what happened, how, what was lost)
- Most states have disclosure laws, no federal law

### Data Protection Principles

- data protection - European Union
- European Union Data Protection Directive (EUDPD) - old
- General Data Protection Regulation (GDPR); 우리 회사 PII ㅋㅋㅋㅋㅋ
- In US, consumers must opt-out (choose not to participate - meaning if you don't choose, US considers as opt-in)

#### European Union Privacy Law

- consumers must opt-in (choose to participate - otherwise it will not be opt-in)
- three conditions must be met for processing personal data:
  - transparency: consent, including purpose and recipients (must opt-in; hence needs consent)
  - legitimate purpose
  - proportionality (비례?)

#### Safe Harbor Principles; 안전 항구 규칙

- Non-EU firms can meet EUDPD requirements by:
  - **Have been replaced, still helpful to understand**

1. **Notice**: inform customers of data collection and purpose
   1. 데이터 수집과 목적에 대해서 알려야 한다
2. **Choice**: can opt out of collection and transfer of data
   1. 어느 데이터 수집을 거부 할지 선택 가능하다
3. **Onward transfer**: third parties must follow principles
   1. 해당 선택들은 이후 제 3자에게도 해당된다
4. **Security**: Reasonable efforts to prevent loss of data
   1. 보호 하기 위해 노력해야 한다
5. **Data integrity**: Relevant and reliable for purpose it was collected
   1. 데이터 수집 목적에 걸맞은 용도로 사용되어야만 한다.
6. **Access**: Customers can access data and correct/delete
   1. 유저가 해당 데이터를 정정하고 삭제할 수 있어야 한다
7. **Enforcement**: Effective means for enforcing rules

### GDPR (2018)

Several major changes:

1. Personal Data elements are anything that can be linked back to a subject, including cookies
   1. 개인 정보는 해당 사용자에게 연결 될 수 있는 모든 정보들을 포함한다 (쿠키 포함)
2. Individuals must have full access to how data is processed in a clear manner
   1. who is asking for the data
   2. what the data will be used for
   3. how long can it be kept (사용기간)
   4. if and where it will be transferred internationally (누가 사용할지)
   5. right to access, correct, or erase
   6. right to withdraw consent, even after collection
   7. right to lodge a complaint

### California Consumer Privacy Act of 2018 (AB 375)

Similar to GDPR

individuals still must opt out but they have rights: 즉 GDPR과는 다르게 opt-out is default

- right to know (access to data and how it's used)
- right to delete (some exceptions)
- right to opt out of sale of information (정보 판매 방지 가능)
- right to non-discrimination if they don't want data sold (정보 판매 거부에 대한 불이익 없음)

## Security Standards

### ISO (International Organization for Standardization)

- five year review cycle

Relevant area is under JTC 1 - Information Technology

- Subcommittee 7 (Software and Systems Engineering)
- Subcommittee 27 (IT Security Techniques)

Prominent ISO Standards for CSSLPs - **See page 64**

### ISO 2700X Series

For information security

Includes vocabulary, code of practice, implementation guidance, metrics, and risk management
 - ISO 가 다 그렇듯 용어, 규칙, 설치 가이드라인, 위험 관리 등등을 포함하고 있으

### ISO 15408 Common Criteria / Evaluation Assurance Levels (EAL)

Functional and assurance requirements

Claims can be made about the product that can be evaluated and verified
 - 해당 제품에 대해 측정가능하거나 확인가능한 사항등에 대해서 claim 이 가능하다 
 - 소프트웨어 보안 스크립트 테스팅 같은거 말하는듯

- **TOE**: Target of Evaluation - product or system being evaluated
  - 측정 대상
- **ST**: Security Target - security properties of a TOE
  - 측정 대상의 보안 목표
- **PP**: Protection profile - set of security requirements associated with a certain class of product
  - products in the same class can be compared more easily

higher EAL != better security
주의사항: 높은 EAL 이 반드시 좋은 보안을 뜻하는것은 아니다 (당연히)

### ISO 9126 Software Engineering Product Quality

- four parts to define a quality model
- Quality of use metrics for specific scenarios
  - Functionality; 기능성
  - Reliability; 신뢰성
  - Usability; 사용성
  - Efficiency; 효율성
  - Maintainability; 관리성
  - Portability; 이동성

### ISO 12207 Systems and Software Engineering - Software Life Cycle Processes

- set of processes each having its own activities, tasks, and outcomes

### ISO 15504 Information Technology - Process Assessment

SPICE/SPICD - Software Process Improvement and Capability Determination

### NIST

National Institute of Standards and Technology

Computer security division

- Federal Information Security Management Act of 2002 (FISMA)
  - 정부 컴퓨터 관련 보안 법 (위 참고)
  - 이거 이후로 FIPS는 모두 정부 관련 사업처들이 따라야함

Information Technology Laboratory (ITL)

- Security bulletins 6x/yr
- Interagency/internal reports (NISTIRs): technical research

#### Federal Information Processing Standards (FIPS)
국가 정보 처리 규칙: 모든 정부 에이전시와 컨트랙터들 모두 반드시 따라야 하는버이며, 얕지만 넓은 스코프를 가지고 있음
- mandatory reqs on fed agencies and specific contractors
- few but broad in authority and scope
- Since FISMA, all aspects are mandatory and waivers are not allowed

#### NIST SP 800 Series

- more commonly used by industry (정부보다는 사업체들에 더 해당됨)
- communicate results of research/guidelines assoc with securing systems
  - 시스템 보안을 위한 관련 리서치및 가이드라인의 결과에 대해 이야기함; 좋은지 나쁜지, 개선점이 있는등
- incl. cryptographic protocols, security reqs, risk mgmt framework, governance, etc

#### Industry

- SAFECode - 많은 애자일 개발 관련 회사들에게 가장 중요한 것
  - Industry-backed
  - increase comm. between firms on software assurance
  - share best practices that have been successful
    - 가장 좋은 방법에 대해서 공유함
  - **SAFECode Releases Software Security Guidance for Agile Practitioners**
    - 애자일 사용자들을 위한 소프트웨어 보안 가이드를 발표함
  - valuable to large and small firms

## Secure Software Architecture

### Security Frameworks

#### COBIT - Control Objectives for Information and Related Technology
정보와 관련 기술을 위한 목적 결정

Published by ISACA (Information Systems Audit and Control Association)

- bridge gap between control reqs, tech issues, and business risks
  - 필요 사항 결정, 기술적 문제 그리고 사업적 위험 사이에 존재하는 갭들을 연결해줌
- Latest is COBIT 2019 (book explains COBIT 5)

##### COBIT 5 Principles

1. Meeting stakeholder needs; 이해 관계자의 필요 충족  (비지니스)
2. covering the enterprise end to end; 사업 관련 사항 모든것을 커버해야함 (비지니스, 컨트롤)
3. applying a single, integrated frmwrk; 통합 프레임워크 (기술)
4. enabling a holistic apprch; 전체적 접근 허가 (컨트롤)
5. separating governance from mgmt; 관리에서 통치 분리 (컨트롤)

#### COSO - Committee of Sponsoring Organizations of the Treadway Commission

- five private-sector orgs in response to Treadway Commissions report on fraudulent financial reporting
- Enterprise Risk mgmt integrated frmwrk to assess control systems
- five components/principles
  - control env
  - risk assmnt
  - ctrl activities
  - info and communication
  - monitoring

#### ITIL - Information Technology Infrastructure Library

- aligning IT services with bus. needs

##### Five volumes

1. ITIL Service Strategy
2. ITIL Service Design
3. ITIL Service Transition
4. ITIL Service Operation
5. ITIL Continual Service Improvement

#### Zachman

- matrix frmwrk to define an enterprise

#### SABSA - Sherwood Applied Business Security Architecture (SABSA)

- frmwrk and methodology for risk-driven enterprise infosec architectures
- similar to Zachman
- Goal: all reqs, including security reqs, can be derived from business reqs
- Works well with SDLC

#### SDLC

Using some kind of process-based lifecycle results in greater security

- partly due to models
- partly due to opportunities for process improvement on models

#### SEI CMMI (Software Engineering Institute - Capability Maturity Model Integration)

- rates process maturity on a 1-5 scale
- Three primary areas: product/service dvlpmnt, service establishment/mgmt, product/service acquisition
- **framework for business process improvement**: improving operational processes

##### Process Maturity Levels 📝

1. **Initial:** uncontrolled, results unpredictable
2. **Managed:** established, typically reactive
3. **Defined:** characterized for org, proactive
4. **Quantitatively Managed:** measured and controlled
5. **Optimizing:** process improvement

#### OWASP - already familiar with :)

#### OCTAVE - Operationally Critical Threat, Asset, and Vulnerability Evauluation

- tools, techniques, methods for risk-based infosec assmnt
- Three phases: build asset-based threat profiles, identify infra vulns, dvlp security strategy

#### BSI - Build Security In

- US Dep of Homeland Security
- info on research, best practices, generic principles for software security
- collaborative effort for devs, architects, infosec practitioners to build security into SDLC

## Trusted Computing

- developed and promoted by trusted computing group (TCG)
- Has a trusted platform module (TPM) with encryption key that is only accessible through the TPM chip
- controversy: could the machine be secured from its owner?

### Principles

1. security
2. privacy
3. interoperability
4. portability of data
5. controllability
6. ease of use

#### Ring Model

- system method
- protect data/functionality from errors and malicious behavior
- ring can only interact within itself or with adjacent rings

#### Reference Monitor (reference validation mechanism)

- access control methodology
- mediates interaction between subjects/objects
- 📝 three qualities are req:
  - no path around it, always invoked (complete mediation)
  - tamper-proof
  - small enough to be verifiable

#### Protected Objects

- existence may be known, cannot be interacted with directly
- must use protected subsystem with specific procedures and a security policy

### Trusted Computing Base (TCB)

- combination of software/firmware/hardware to ensure security
- includes kernel and reference monitors, **not applications**
  - if application becomes compromised, it would not affect TCB

### Trusted Platform Module (TPM)

- secure storage of crypto. keys and platform auth - on a chip

### Microsoft Trustworthy Computing Initiative (2002)

Four pillars:

1. security (including social dimension)
2. privacy
3. reliability
4. business integrity

## Acquisition

Terms:

- Commercial off-the-shelf (COTS)
- Government off-the-shelf (GOTS)

### Build vs buy

- some things are best purchased (database software)
- mission-critical or proprietary business info is best built

### Outsourcing

- can find cheaper programmers/people but most of a project's cost is not from the coders
- has challenges due to geographic separation

### Contractual Terms and SLAs

- should include references to security ctrls/standards
