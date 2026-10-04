# Task 9 — Conditional Access

## Objective

Understand how Microsoft Entra Conditional Access evaluates sign-in conditions and applies access controls.

---

# Task 1 — Conditional Access Concepts

## Key Concept

Conditional Access uses **IF/THEN logic** to make access decisions based on conditions such as:

- User or group
- Application
- Location
- Device state
- Sign-in risk

## Examples

IF User is signing in  
AND sign-in is from outside the trusted network  
THEN Require MFA

IF User is accessing company data  
AND device is not compliant  
THEN Block access

IF Sign-in risk is high  
THEN Require stronger authentication

IF user is in Manager group  
AND user is signing in  
THEN Require a compliant/domain-joined device

## Lab Limitation

The DomConsultancy lab uses **Microsoft Entra ID Free**.

The Conditional Access portal was accessible for exploration; however, creating and enforcing the full Conditional Access policies required for this lab requires an appropriate Microsoft Entra ID Premium licence.

## Evidence 25 — Conditional Access Overview

<img width="630" height="457" alt="Screenshot 2026-10-01 153348" src="https://github.com/user-attachments/assets/a95c2480-3d48-4dfa-a701-31a5fa2d0543" />


---

# Task 2 — Authentication Strengths

## Objective

Review Microsoft Entra authentication strengths and understand how authentication requirements can be differentiated based on security needs.

## Available Built-in Authentication Strengths

- Multifactor authentication
- Passwordless MFA
- Phishing-resistant MFA

## Observation

The DomConsultancy tenant exposed built-in authentication-strength definitions.

At the time of testing, the authentication strengths were not associated with a Conditional Access policy.

This demonstrates the distinction between defining available authentication strengths and enforcing a specific authentication strength through Conditional Access.

## Evidence 26 — Authentication Strengths

<img width="719" height="431" alt="Screenshot 2026-10-01 154702" src="https://github.com/user-attachments/assets/d806156e-89bb-4611-9bbc-4cbb9bb13bec" />


---

# Task 3 — Named Locations

## Objective

Understand how named network locations can be used with Microsoft Entra Conditional Access to identify trusted or specified network locations.

## Observation

The Named Locations page was accessible in the Microsoft Entra portal, but the options to create an IP-ranges location were unavailable in the current Entra Free lab environment.

## What I Learned

Named Locations can be used by Conditional Access to define network locations using:

- IP address ranges
- Geographic locations

These locations can then be referenced as conditions within Conditional Access policies.

### Example

IF user is signing in from outside a trusted location  
THEN require MFA

## Lab Limitation

The DomConsultancy lab uses Microsoft Entra ID Free, which limited the configuration options available for Named Locations during this exercise.

## Evidence 27 — Named Locations

<img width="786" height="432" alt="Screenshot 2026-10-01 155141" src="https://github.com/user-attachments/assets/ecded038-c9b3-4a32-b8f4-de1bf5066b24" />


---

# Conditional Access Outcome

The Conditional Access investigation provided practical understanding of how identity, device, location and authentication conditions can be used to make access decisions.

The lab demonstrated:

- Conditional Access IF/THEN decision logic
- Authentication strength concepts
- Named Locations
- Security policy conditions
- Licensing limitations affecting Conditional Access configuration

Although the Microsoft Entra ID Free licence limited full policy creation and enforcement, the Conditional Access environment and available security controls were investigated and documented.
