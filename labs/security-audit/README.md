# Lab 01 - Security Audit

## Objective
Conduct an internal security audit for a fictional company (Botium Toys) by assessing existing controls, identifying compliance gaps, and making remediation recommendations based on the NIST CSF.

## Scenario Summary
Botium Toys is a small business toy company with a rapidly growing internet presence. Their IT manager has decided that an internal IT audit need to be done. She is worried about maintaining compliance, especially regarding conducting business in the European Union, and business operations. My task is to review the IT manager’s scope, goals, and risk assessment report. Then, perform an internal audit by completing a controls and compliance checklist.

## Scope & Goals
- Scope: entire security program at Botium Toys
- Goal: assess controls & compliance against PCI DSS, GDPR, SOC type 1/2

## Methodology
1. Reviewed asset inventory
2. Completed Controls Assessment checklist
3. Completed Payment Card Industry Data Security Standard (PCI DSS) Compliance checklist
4. Completed General Data Protection Regulation (GDPR) Compliance checklist
5. Completed System and Organizations Controls (SOC type 1, SOC type 2) Compliance checklist
6. Summarized Recommendations

## Control Assessment Findings
| Control | In Place? | Notes |
|---------|-----------|-------|
|Least Privilege| No | All employees have access to customer data |
|Disaster recovery plans| No | Company has no disaster recovery plan in place |
|Password policies| No | Password policies exist but are not complex |
|Separation of duties| No | No separation of duties in place |
|Firewall| Yes | Firewall set to an appropriate configuration |
|Intrusion detection system (IDS)| No | No IDS installed |
|Backups| No | Critical data is not backed up |
|Antivirus software| Yes | Software installed and actively monitored |
|Manual monitoring, maintenance, and intervention for legacy systems| No | No regular schedule in place |
|Encryption| No | Credit card information is not encrypted |
|Password management system| No | No policy enforcing password minimum |
|Locks (offices, storefront, warehouse)| Yes | Sufficient locks in place |
|Closed-circuit television (CCTV) surveillance| Yes | Up-to-date surveillance in place |
|Fire detection/prevention (fire alarm, sprinkler system, etc.)| Yes | Functioning systems in place |

## PCI DSS Findings
| Best Practice | In Place? | Notes |
|---------------|-----------|-------|
|Only authorized users have access to customers’ credit card information.| No | All employees have access to credit card data |
|Credit card information is stored, accepted, processed, and transmitted internally, in a secure environment.| No | Data stored locally on internal database |
|Implement data encryption procedures to better secure credit card transaction touchpoints and data. | No | Credit card data is not encrypted |
|Adopt secure password management policies.| No | No password management policy in place |

## GDPR Findings
| Best Practice | In Place? | Notes |
|---------------|-----------|-------|
|E.U. customers’ data is kept private/secured.| No | All employees can access customer data |
|There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach.| Yes | A plan is in place to notify within 72 hours |
|Ensure data is properly classified and inventoried.| Yes | Data is properly stored |
|Enforce privacy policies, procedures, and processes to properly document and maintain data.| Yes | Policies and procedures well enforces |

## SOC type 1 & SOC type 2 Findings
| Best Practice | In Place? | Notes |
|---------------|-----------|-------|
|User access policies are established.| No | All employees can access all data |
|Sensitive data (PII/SPII) is confidential/private.| No | All employees can access all customer PII/SPII |
|Data integrity ensures the data is consistent, complete, accurate, and has been validated.| Yes | IT department ensures integrity of data |
|Data is available to individuals authorized to access it.| Yes | IT department ensures avalibility of data |

## Recommendations
Multiple controls need to be implemented at Botium Toys in order to improve security posture including installing an Intrusion Detection System (IDS), encrypting sensitive data, and creating disaster recovery plans. Most importantly is to fix compliance issues in order to adhere to the Payment Card Industry Data Security Standard, including actions like limiting access to customers PII, SPII, and credit card information; as well as implementing a password management system and enforcing a password policy. 

# Lessons Learned
Performing this lab helped me gain experience auiditing a company and showed me how quickly compliance gaps add up. The compliance gaps that stood out to me the most were around PCI DSS. Botium Toys were handling customer credit card data but had no encryption or access control measures in place. The biggest takeaway was the difference between a control existing on paper and actually being enforced. Several policies were listed as being in place but were not actively being enforced. When conducting an audit, that distinction matters as much as whether the control exists at all. Going foward I would like to explore how organizations prioritize which compliance gaps to close first when they have limited resources.
