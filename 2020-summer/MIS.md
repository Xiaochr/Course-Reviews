# 管理信息系统

## Introduction

- Technology evolution

- IoT - Cloud - Big data

- In the age of big data
    - Phase1: pixels. Digital business(digitalization, BA)
    - Phase2: imaging. Algorithmic business(BA+AI)

- Five Key Features of Nowadays Technologies and Applications
    - Mobility
    - Virtual reality
    - Extreme data
    - Personalization
    - Social network

- IT fusion and big data
    - Technology pervasiveness
    - Technology transparency

- **Big data**
    - Data aspect
        - 4Vs: Volume, Variety, Value, Velocity
    - The problem nature aspect
        - High data pixels, external data, global view
    - The business aspect
        - BA enabling

- MIS is a computer-based system (e.g., software package) composed of interacting components for performing certain tasks in business and managerial contexts. 

- Data, Information, Knowledge

- IS vs. Management issues
    - OLTP: tables, queries, automation
    - OLAP: slicing, tracing, dimension
    - KDD: mining, intelligence

- Value chain

- MRP, MRP2, ERP, VCRP
    - 前三个是internal value chain，最后一个是external

- SCM and ERP
    - Material requisition 物料需求管理
    - Production resource 生产资源管理
    - Enterprise resource 企业资源管理
    - External supply chain 供应链管理

- **What is ERP?**

- **CRM**

- BI

- BA
    - Basic methods: clustering, classification, association, patterns

## Association Rules

- Basic measures
    - Degree of support (Dsupp) $|XY|/|D|$
    - Degree of confidence (Dconf) $|XY|/|X|$

- Valid rules
    - Iff $Dssup(X \rightarrow Y) \geq minsupp$ and $Dconf(X \rightarrow Y) \geq minconf$

- **Apriori**
    - 从1 itemset开始，找出符合Dsupp规定的，然后对找到的每个itemset中的association检查Dconf。

- AR
    - Classical (boolean)
    - Extensions
        - Generalized AR (between item classes)
        - Quantitative AR (continuous data)
        - Temporal AR (隔一段时间的)
        - Classification based on AR
        - Associative patterns

## Modeling and Decisions for Systems Development

- **Waterfall model**
    - Inception, analysis, design, coding, run

- **b model**
    - Development: inception, analysis, design, coding
    - Maintenance: coding, run, evaluation, analysis, design, coding

### Business modeling

- Model
    - Static aspect (data modeling, RDB)
    - Dynamic aspect (JSD)
    - Business process
    - Business rules

- **JSD**(Jackson System Development) core model
    - Three basic constructs
        - sequence: occur in sequence and once
        - selection: one of xx occurs once
        - iteration: occur zero, one or more times

## **Outsourcing**

- Drives

- Risks

## **Cloud computing**

- Cloud computing as a service

- Challenges
    - Variable cost
    - Reliability
    - Compatibility
    - Safety
    - Possible opportunities

---

[Back to top](#管理信息系统)