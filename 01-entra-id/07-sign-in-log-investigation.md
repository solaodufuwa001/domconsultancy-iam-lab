# Task 7 — Sign-in Log Investigation

## Objective

Investigate user authentication activity using Microsoft Entra sign-in logs and verify the authentication method used by a test user.

---

## Test 1 — Successful Sign-in Investigation

### Investigation

| Field | Finding |
|---|---|
| User | Sarah Williams |
| MFA requirement | Succeeded |
| First factor | Succeeded |
| Overall sign-in | Successful |
| Authentication details | Previously satisfied |

### Finding

The sign-in event for Sarah Williams was reviewed in Microsoft Entra sign-in logs.

The Authentication Details section showed that Security Defaults were applied and that both the first-factor requirement and MFA requirement were successful.

**First factor:** The initial authentication requirement used to establish the user's identity, typically a username and password.

**MFA:** An additional authentication factor required after the first factor, providing an additional layer of identity verification.

The authentication entries displayed **"Previously satisfied"**, indicating that the relevant authentication requirement had already been satisfied during the authentication session.

### Security Relevance

Sign-in logs provide security administrators with visibility into authentication activity and can be used to investigate suspicious or unusual sign-in behaviour.

## Evidence 18 — Sarah Sign-in Authentication Details

<img width="426" height="262" alt="Screenshot 2026-09-30 145519" src="https://github.com/user-attachments/assets/8a95b8cd-abff-4959-a740-c9595f90eee1" />


---

# Test 2 — Failed Sign-in Investigation

## Scenario

A failed authentication event was deliberately generated using the Sarah Williams test account to practise investigating failed sign-ins.

## Investigation Finding

| Field | Finding |
|---|---|
| Status | Failure |
| Authentication requirement | Single-factor |
| Error code | 50126 |
| Failure reason | Invalid username or password |

## Finding

A failed authentication event was identified for the Sarah Williams test account.

The event had a status of **Failure** and sign-in error code **50126**. The recorded failure reason was **invalid username or password**.

The authentication requirement was recorded as single-factor authentication because the supplied credentials failed validation before the authentication process progressed to the MFA stage.

The event was therefore assessed as an **invalid-credential authentication failure**.

No conclusion of malicious activity was made from this single event.

## Analysis Conclusion

The event demonstrates that a failed password authentication prevents the sign-in process from progressing to MFA.

Additional events and contextual information would be required before determining whether a pattern represents suspicious activity.

## Evidence 19 — Failed Sarah Sign-in

<img width="648" height="396" alt="Screenshot 2026-09-30 150705" src="https://github.com/user-attachments/assets/b2458a1e-5f63-4959-9261-bd6a3979520d" />



<img width="435" height="452" alt="Screenshot 2026-09-30 151357" src="https://github.com/user-attachments/assets/ca887674-3327-4e59-9fe0-26e49ff6fae3" />




<img width="408" height="406" alt="Screenshot 2026-09-30 151411" src="https://github.com/user-attachments/assets/9260379f-c85c-4759-baf7-12336b405346" />




<img width="418" height="230" alt="Screenshot 2026-09-30 151424" src="https://github.com/user-attachments/assets/655d3023-6426-4764-a92d-2d46559d3cd9" />

---

## Location Analysis

The failed sign-in event was associated with an IP address that Microsoft Entra geolocated to **Nottingham, GB**.

The event was not routed through Global Secure Access.

IP-based location was treated as contextual information rather than definitive evidence of the user's physical location.

No malicious activity was concluded from the location alone.

## Evidence 20 — Failed Sign-in Location Information


<img width="387" height="216" alt="Screenshot 2026-09-30 152306" src="https://github.com/user-attachments/assets/5efea754-7eeb-40db-aa63-21c6decc6128" />

---

## Device Analysis

The failed sign-in originated from a browser using **Chrome 153 on Windows 10**.

The device was recorded as **not managed** and **not compliant**. No Entra device join information was associated with the event.

The device status was treated as contextual information and not, by itself, evidence of malicious activity.

## Evidence 21 — Failed Sign-in Device Information


<img width="389" height="247" alt="Screenshot 2026-09-30 152508" src="https://github.com/user-attachments/assets/a5ce6699-f69b-49c3-bc6f-8268551060b7" />


---

# Identity Investigation Summary

| Attribute | Finding |
|---|---|
| User | Sarah Williams |
| Application | Azure Portal |
| Result | Failed |
| Error | 50126 — Invalid username/password |
| Authentication stage | Single-factor |
| Location | Nottingham, GB (IP-based) |
| Browser | Chrome 153 |
| Operating System | Windows 10 |
| Managed | No |
| Compliant | No |

## Analyst Conclusion

The event was assessed as a failed authentication caused by invalid credentials.

The event alone does not provide sufficient evidence of malicious activity.

Location and device information were reviewed as contextual indicators rather than definitive evidence of compromise.

Further investigation would be required if repeated failures or other suspicious indicators were observed.
