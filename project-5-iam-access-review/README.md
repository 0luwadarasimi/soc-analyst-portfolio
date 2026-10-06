# Quest 5 - IAM Access Review (Least Privilege Audit)

## Summary
I built a small simulated company on an Ubuntu Server VM with three departments (Finance, HR, IT) and one employee in each. I then simulated a common real-world mistake: an HR employee (bob) was added to the Finance group by accident. I audited group membership, found the violation, proved the impact by reading a confidential file as bob, then removed the access and verified the fix.

> Note: all users, groups, and files are synthetic and exist only in my home lab.

## Skills demonstrated
- Access review and group membership auditing
- Identifying least privilege violations
- Linux user, group, and file permission management
- Verifying a remediation with evidence

## Setup
Groups created: `finance`, `hr`, `it-admin`.
Users created: `alice` (finance), `bob` (hr), `carol` (it-admin).
Department folders in `/srv/company/` were locked to their own group with `chmod 770`.

![Setup]

## The mistake
I added bob (HR) to the finance group and placed a fake payroll file in the finance folder.

```
sudo usermod -aG finance bob
```

![Mistake planted]

## Audit finding
Reviewing group membership showed that `finance` contained `alice,bob`. Bob works in HR and has no business need for Finance data.

```
getent group finance hr it-admin
```

![Audit]

## Impact
Bob could read the confidential payroll file, which confirmed the excess access was real.

```
sudo -u bob cat /srv/company/finance/payroll.txt
```

![Impact]

## Remediation
I removed bob from the finance group and re-tested. Finance now contains only alice, and bob gets `Permission denied`.

```
sudo gpasswd -d bob finance
```

![Fixed]
## Lessons learned
- Least privilege means people only get the access their job requires.
- Regular access reviews catch mistakes like this before they become data leaks.
- Always verify a fix with evidence, not just by running the command.


