# IAM Access Review: Least Privilege Audit

**Type:** Access Control Lab | **Environment:** Ubuntu Server (simulated company) | **Status:** Completed

---

## Summary

I built a small simulated company on an Ubuntu Server VM with three departments (Finance, HR, IT), one user in each. Then I planted a common mistake: an HR employee (`bob`) was added to the Finance group. I found it in an access review, proved the impact, removed the access, and verified the fix.

> All users, groups, and files are synthetic and exist only in my home lab.

---

## Setup

**Groups:** `finance`, `hr`, `it-admin`  
**Users:** `alice` (Finance), `bob` (HR), `carol` (IT Admin)

```bash
sudo groupadd finance && sudo groupadd hr && sudo groupadd it-admin

sudo useradd -m -G finance alice
sudo useradd -m -G hr bob
sudo useradd -m -G it-admin carol

sudo mkdir -p /srv/company/{finance,hr,it}
sudo chown root:finance /srv/company/finance
sudo chown root:hr /srv/company/hr
sudo chown root:it-admin /srv/company/it
sudo chmod 770 /srv/company/finance /srv/company/hr /srv/company/it

echo "Synthetic payroll data" | sudo tee /srv/company/finance/payroll.txt
```

---

## Investigation

**1. The mistake (planted):**
```bash
sudo usermod -aG finance bob
```

**2. Audit:** I listed group members and found `bob` (HR) in `finance`.
```bash
getent group finance hr it-admin
```

**3. Prove the impact:** `bob` could read the confidential payroll file.
```bash
sudo -u bob cat /srv/company/finance/payroll.txt
```

**4. Remediate:** I removed `bob` from the Finance group.
```bash
sudo gpasswd -d bob finance
```

**5. Verify:** I repeated the read. `bob` now gets "Permission denied".
```bash
sudo -u bob cat /srv/company/finance/payroll.txt
```

---

## Skills Demonstrated

- Access reviews and group membership auditing
- Spotting least-privilege violations
- Linux user, group, and file permission management
- Proving impact and verifying a fix with evidence

---

## Next Steps

- Add screenshots of each step's output
- Write a script that flags unexpected group members

---

*All data in this lab is synthetic and was created in a controlled home-lab environment for learning purposes.*
