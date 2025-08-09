# enforcing-mfa-privileged-accounts
Got it — here’s the **summary rewritten in first-person** so it reads as *your* project and motivations:

---

# Enforcing MFA for Privileged Accounts (IA-2(1)) – Summary

**Purpose**
I built this lab to show how to use **Policy-as-Code** with **Rego** and **Conftest** to automatically enforce **Multi-Factor Authentication (MFA)** for administrator accounts. I simulated IAM settings, wrote a policy to detect missing MFA, and ran automated tests to ensure compliance.

**Why I Did This**
Privileged accounts can reconfigure security, access sensitive data, and disable monitoring. If compromised, the damage can be severe. MFA reduces this risk by requiring a second factor even if a password is stolen.
A real-world example that inspired me: In 2022, a subcontractor’s admin account at Okta lacked MFA, which allowed attackers to access internal systems. I wanted to see how a simple automated policy could have caught that.

**What I Learned**

* How to identify privileged users in a config file.
* How to write a Rego rule that enforces MFA.
* How to use Conftest to test IAM configurations.
* How technical enforcement connects to GRC requirements like IA-2(1).

**How I Did It**

1. **Setup** – Installed Terraform & Conftest in a GitHub Codespaces environment.
2. **Create Input** – Wrote `iam_config.json` with users, roles, and MFA status.
3. **Write Policy** – Created `policy/require_mfa.rego` to flag any admin missing MFA.
4. **Run Tests** – Used `conftest test iam_config.json` to detect violations.
5. **Fix & Re-test** – Enabled MFA in configs and confirmed compliance.
6. **Expand** – Added checks for missing or null MFA fields.

**The Outcome**
I now have:

* An automated control enforcing IA-2(1) continuously.
* A repeatable test that works in CI/CD pipelines.
* A concrete example of translating compliance requirements into code and evidence.

---

If you want, I can now also create that **one-paragraph ultra-condensed intro** for the very top of your README so people instantly know what you did and why. That will make the repo feel polished and purposeful.
