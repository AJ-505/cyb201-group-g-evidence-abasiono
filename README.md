# Individual evidence submission — Abasiono Mbat (24120111121)

Group G, Stream 1 · CYB 201 CA 1 — Project G: SQLi Dump + Covert Exfiltration
Authorised lab exercise only (Metasploitable 2 / DVWA and a local practice target on the author's own machine).

This folder is exactly what the brief's submission checkpoint asks for: **your own log, screenshots and contribution form** (Pentesting Workflow guide, step 08 "Submit checkpoint evidence", and step 07 for the naming standard).

## Submitted files

| File | Guide evidence type | What it shows |
|---|---|---|
| `G_AbasionoMbat_SessionLog.txt` | Personal terminal log | The author's own `script`-recorded session: nmap scan, sqlmap confirmation of the `id` injection (four techniques) and full users-table dump, john cracking with rockyou, steghide embed/verify/extract with a byte-for-byte round-trip check (`ROUND-TRIP OK`), ending with a clean `Script done`. The interrupted-then-resumed john run is preserved on purpose. |
| `G_AbasionoMbat_01_Recon.png` | Recon screenshot | nmap service discovery: port 8080 open, Apache httpd 2.2.8 / PHP 5.2.4 fingerprint (verbatim excerpt from the log above). |
| `G_AbasionoMbat_02_Vulnerability.png` | Vulnerability screenshot | sqlmap confirming the `id` parameter is injectable (boolean-based blind + UNION) and fingerprinting the back-end. |
| `G_AbasionoMbat_03_Demonstration.png` | Demonstration screenshot | john `--show`: all five cracked passwords, including the identical-hash pair that demonstrates why unsalted MD5 fails. |
| `G_AbasionoMbat_ContributionForm.pdf` | Contribution form + peer review | What the author personally worked on, factual peer reviews of the four teammates with observed evidence, the peer participation scale, and a note for the instructor. |
| `G_AbasionoMbat_Reflection.pdf` | Individual reflection | What was done, learned, struggled with and contributed. |

`working-files/` holds the underlying artefacts of the chain (dump.csv, hash.txt, cover.jpg, stego_output.jpg, recovered.csv and the john explainer) as backup proof. They are **not** part of the submission zip.

## Honesty note

The author's sqlmap/john/steghide run in the log was a rehearsal against a local practice target on his own machine (his laptop could not host the Metasploitable 2 VM); the group's lab-target evidence is captured by teammates and cross-referenced in the group report. This is stated openly in the report's challenges section and in the contribution form.
