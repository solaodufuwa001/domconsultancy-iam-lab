<img width="854" height="499" alt="Screenshot 2026-09-30 144515" src="https://github.com/user-attachments/assets/d136ba5b-1ee1-4490-b07a-ad7f315f10c3" /># Task 6 — Security Defaults & MFA

## Objective

Verify that baseline identity security controls are enabled in the DomConsultancy Microsoft Entra tenant.

## Configuration

| Setting | Result |
|---|---|
| Security Defaults | Enabled |
| Tenant | DomConsultancy |
| Entra Licence | Microsoft Entra ID Free |
| Purpose | Baseline identity protection and MFA |

## Observation

Microsoft Entra Security Defaults are enabled in the DomConsultancy lab tenant.

Security Defaults provide baseline identity security controls, including multifactor authentication requirements.

## Evidence 15 — Security Defaults Enabled

The screenshot confirms that Security Defaults are enabled for the DomConsultancy Microsoft Entra tenant.

<img width="824" height="464" alt="Screenshot 2026-09-30 143755" src="https://github.com/user-attachments/assets/03169beb-b74b-48a4-b5ca-f82b0ca55b5a" />


---

## MFA Registration Test

### Scenario

Sarah Williams was signed in using her test account.

Because Security Defaults were enabled in the DomConsultancy tenant, Sarah was required to register a multifactor authentication method using Microsoft Authenticator.

The Microsoft Authenticator application was successfully registered and linked to Sarah's account.

**Result: Passed**

## Evidence 16 — Sarah Microsoft Authenticator Registration

<img width="792" height="410" alt="Screenshot 2026-09-30 144412" src="https://github.com/user-attachments/assets/e9b31943-8b46-4416-a70e-ec49ee07e27d" />


---

## MFA Sign-in Test

After registering Microsoft Authenticator, Sarah was signed out and signed in again.

The authentication process required an additional Microsoft Authenticator verification before access was granted.

**Result: Passed**

## Evidence 17 — MFA Sign-in Challenge

<img width="854" height="499" alt="Screenshot 2026-09-30 144515" src="https://github.com/user-attachments/assets/f0984e43-7879-4e10-ba5a-92be56b2c8bc" />


---

## Security Principle Demonstrated

Multifactor authentication provides an additional layer of protection beyond the user's password.

The test confirmed that MFA was enforced during authentication rather than simply being configured in the tenant.

## Outcome

The MFA tests successfully demonstrated that:

- Security Defaults were enabled.
- Sarah was required to register an MFA method.
- Microsoft Authenticator was successfully registered.
- A subsequent sign-in triggered an MFA challenge.
- Access was granted after successful additional verification.
