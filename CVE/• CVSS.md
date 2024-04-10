--- ---
<h2>What is CVSS</h2>
CVSS stands for Common Vulnerability Scoring System. It is a framework used to quantify and assess the severity of computer system security vulnerabilities. CVSS provides an open and standardized method for rating vulnerabilities, allowing organizations to prioritize and address security issues effectively.

The CVSS framework evaluates vulnerabilities based on various factors, including exploitability, impact, and complexity of the attack. It generates a numerical score ranging from 0.0 to 10.0, with higher scores indicating more severe vulnerabilities.

CVSS scores are widely used by security professionals, vendors, and organizations to prioritize vulnerability remediation efforts, allocate resources effectively, and communicate the severity of security vulnerabilities in a standardized manner.

---

CVSS vectors & metrics
```
AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H
```
- AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H
	- AV = Attack Vector
		- N = Network
		- A = Adjacent
		- L = Local
		- P = Physical
	- AC = Attack Complexity
		- L = Low
		- H= Hight
	- PR = Privilege Required
		- L = Low
		- H = High
		- N = None
	- UI = User Interation
		- R = Required
		- N = None
	- S = Scope
		- C = Changed ---> Vuln can reach new system
		- U = Unchanfed ---> Vuln contained to same system
	- C = Confidentiality (CIA triande)
		- H = High
		- L = Low
		- N = None
	- I = Integrity
		- H = High
		- L = Low
		- N = None
	- A = Availability
		- H = High
		- L = Low
		- N = None

Critical   = 9.0 - 10.0
High       = 7.0 - 8.9
Medium = 4.0 - 6.9
Low        = 0.1 - 3.9
None      = 0.0                ---> technically imposible to exploit