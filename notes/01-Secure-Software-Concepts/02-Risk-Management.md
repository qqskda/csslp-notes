# Risk Management

- **assess the impact if an adverse event were to happen decide what could be done to control that impact as deemed necessary**
- 적대적 행위가 발견될시에 어떻게 반응할지, 그리고 어떻게 피해를 최소화 할지에 대해서 생각해 두는것
  
Well formed risk statement includes:

1. asset          - 자원
2. threat         - 위협
3. vulnerability  - 취약점
4. mitigation     - 해결책
5. impact         - 피해 현황
6. probability    - 확률

## Risk

Systematic risk
- fire, theft, software bugs - mitigated through diversification (분산화)
- predictable under stable circumstances (예상 가능함)

Unsystematic risk
- recession, epidemics, protocol design errors
- come from sources that are difficult to predict (예상 하기 힘듬)

### Business risk

- operation of a business as a business
- 사업 관련 리스크: technology management side 가 아닌 정말 사업 관련; 법률, 기술, 사기, 계약 등등

Examples:

- Treasury management (financial risk)
  - holdings in bonds, futures, currencies, etc
- Revenue management
- Contract management
- Fraud
  - deliberate deception (계획 사기)
- Regulatory
- Business continuity
- Technology

### Technology risk

- technology used in development process as well as software functionality
- 기술적 보안, 개인정보, 프로젝트 리스크 관리, 매니지먼트 변화 등등 개발 관련 느낌

Examples:

- Security - protective attributes
- Privacy - attributes that define access/sharing
- Project risk management
- Change management

### Risk controls 위험 관리

- 📝 best method for managing risk in software
  - 소프트웨어에서 위험 관리하는데 있어서 최선의 방법
- 📝 Understanding environment and risk and applying controls should be owned by development team
  - 환경및 위험을 이해하고 관리하는것은 개발 팀이 가지고 있어야 한다.

Three classes:

1. Administrative 
2. Technical
3. Physical

For each class, there are four types of controls

1. Preventative - 예방
2. Detective    - 감지
3. Corrective   - 수정/보안/방어: 최대한 피해 줄이는거
4. Compensating - 보정: 예방에 실패했을 경우, alternative method 를 이용해서 같은 효과를 내는것

#### Preventative 예방 - 최선은 역시 예방

- primary control
- proactive
- best mitigation
- **goal**: stop attack

Examples:

- separation of duties (분업화)
- adequate documentation (서류화)
- physical control over assets
- authorization mechanisms

#### Detective

- reactive
- **goal**: detect presence of attack

Examples:

- logs
- audits
- inventories

#### Corrective

- after a vulnerability is exploited
- **goal**: reduce total impact

#### Compensating

- when primary controls fail
- reactive
- alternative method: find other ways to do risk control

Example: separation of duties is a preventitve control to prevent fraud, financial review of reports is an after the fact compensating control

#### Controls framework

- managing risk as part of a complete system

## Qualitative

- **Subjectively determine impact of an event - involves experts and group consensus**
  - 전문가와 그룹끼리 합의를 봐서 주관적으로 (예상) 피해를 측정하는것.

Two aspects: impact and probability (피해및 가능성)

### Qualitative matrix

#### Failure mode effects analysis (FMEA) - 고장형태 및 영향분석 - 이거 우리 회서 Jira QA? 점수 매기는 방식

- assess failures and effects on the system (실패및 영향을 측정)
- for each issue, elements are defined (각 이슈마다 정의를 내림)
- severity of risk is defined (1-10)
- probability (1-10)
- detectability (1-10)
- calculate product (over 200 / 1000 worth looking at)

### Quantitative

- **Objectively determine impact of an event - involves use of metrics and models**
  - 예전에 있던 손해와 트랜드를 바탕으로 미래 손해를 예측 하는 방식 (객관적인 데이터를 통해)

- use historical loss and trends to predict future loss
- highly dependent on historical loss data
- assuming constant risk rate is not an agreed upon concept

key info:

- important to come to consensus on values being used (사용되는 가치에 대한 합의에 도달하는게 중요)
- use consistent values
- models can never replace judgement and experience, but can enhance decision making (의사 결정에 도움이 되는정도)

### Single loss expectancy (SLE) - 간단한 손해 예상

📝 SLE = asset value \* (exposure factor or duration)

### Annualized rate of occurrence (ARO) - 연평균 발생치

📝 ARO = number of events / number of years covered

### Annualized loss expectancy (ALE) - 연평균 손해 예상

📝 ALE = SLE \* ARO

## Residual Risk Model

- Absolute security is not achievable

Example:

- potential loss of $100k
- firewall blocks 95%
- IDS (intrustion detection system) is 80% effective
- IRT (incident response team) is 50% effective
- 100k \* 95% + (5k \* 80% \* 50%) = 97k with 3k residual

### ROI

- 📝 ROI % = (avoided loss - control cost) / control cost \* 100
- 📝 ROI time = avoided annual loss / annual control cost

## Governance, Risk, and Compliance 거버넌스, 위험 및 규정 준수

- **Governance**: sum of executive actions that manage risk (리스크 관리를 위한 실행 조치 행동의 합)
  - need to comply with laws and regulations, so GRC terms are used synonomously
- **Compliance**: activities associated with external requirements (contractual, policy, strategic, industry, regulations, laws)
  - 외부 요구사항에 관련된 것들 (계약, 정책, 작전, 사업, 법...)
- **Conformance - 적합성**: activities associated with internal requirements (org policies/standards)
  - 내부 규칙
- Compliance gets priority over conformance
  - 당연히 규정이 적합성보다 우선순위 (외부 규칙이 먼저)
  - many reasons, primary being penalties (많은 이유가 있지만 가장 큰 이유로는 패널티 때문)

### Legal

Two key legal issues with significant risk

1. intellectual property
   1. legal action provides some protection but not against unknown criminals
2. data breach

### Standards

- established norms (확립된 규범)
- **goal**: define rules to ensure specified level of quality (즉 규범을 세움으로써 퀄리티 수준을 유지할 수 있음)

## Risk Management Models

### General Risk Management Model

1. Asset identification
   1. includes classification
2. Threat assessment
   1. threats and vulnerabilities for each asset
   2. likelihood of occurrence
3. Impact determination and quantification (영향 결정 및 정량화)
   1. Tangible: financial loss, physical damage
   2. Intangible: reputation
4. Control design and evaluation
   1. Decide which controls to implement
   2. And how to evaluate
5. Residual Risk Management
   1. Identify additional controls needed to reduce residual risk
   2. 방어벽, 해킹 방어 시스템 등등의 추가적인 관리 방법을 도입해서 잔류 위험 최대한 줄이기

### Software Engineering Institute Model

1. Identify - list potential risks
2. Analyze - impact, probability - classify and prioritize risks
3. Plan - Decide actions to take and implement mitigation
4. Track - Monitor and review risks and mitigations
5. Control - make corrections as needed
