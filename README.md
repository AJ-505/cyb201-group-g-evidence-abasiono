# Group G evidence folder — teammate brief

You do not need to edit the group report. It is finished, and the instructor gets one group PDF from the group. Your job is your own evidence folder, and this repository shows you exactly what goes in one.

## Step 1: copy, do not edit in place

Fork or clone this repository, then delete Abasiono's six evidence files from your copy. Keep the folder names as your guide. Never upload a file with my name on it.

## Step 2: six files, your name on each

Use this naming format exactly, with your own name after the G. No spaces, lowercase `.png`, one log per person.

```
G_YourName_01_Recon.png           the recon screenshot
G_YourName_02_Vulnerability.png   the vulnerability screenshot
G_YourName_03_Demonstration.png   the demonstration screenshot
G_YourName_SessionLog.txt         your terminal log
G_YourName_Reflection.pdf         your reflection, half a page
G_YourName_ContributionForm.pdf   your contribution form and peer review
```

Real example from my folder: `G_AbasionoMbat_03_Demonstration.png`.

## Step 3: where each file comes from

- **SessionLog.txt.** Start your session with `export PS1="24120111121> "` (your own number), then `script ~/yourname_log.txt`, then `date`, `whoami`, `hostname`. Run your chain step inside that window. End with `exit`, then check the file with `ls -lh`. Keep your mistakes in the log. The guide asks for this.
- **01_Recon.png.** A screenshot of your own terminal output showing a real discovery or enumeration. My example is an nmap scan that found the web port and the Apache and PHP versions.
- **02_Vulnerability.png.** A screenshot showing the unsafe parameter being confirmed. My example is sqlmap saying the id parameter is injectable.
- **03_Demonstration.png.** A screenshot of the key result of your step. My example is john listing all five cracked passwords.
- **Reflection.pdf.** Half a page, your own words. What you did, what broke, what you learned.
- **ContributionForm.pdf.** Copy my form and rewrite it for yourself. Keep the same four parts: what you personally worked on, what each of the other four members contributed and what evidence you saw of it, the 1 to 5 participation scale, and a short note for the instructor. Set the scores you actually believe. The form is your honest view, so it does not have to match mine.

## Step 4: what goes in the zip, and what does not

The zip holds **exactly the six evidence files above**. Nothing else.

Do **not** include:

- this README, or any other markdown file (`.md`)
- `.gitignore`
- the `working-files` folder (my cover image, dump, hashes and recovered file — backup only)

## If your laptop cannot run the VM

Say so in your reflection and in the note for the instructor inside your contribution form. Say where you ran your chain and where the lab-target evidence came from. Rehearsing on your own machine is fine. Claiming a lab run you did not do is not.

## How you submit

Email your lecturer two attachments. Nothing else.

```
1. G_YourName.zip        your six evidence files only
2. G_Group_G_Report.pdf  the group report, which the group submits once
```

Only the first one is yours to build. The group PDF comes from the group report page, which is already finished, so do not attach your own copy of the report and do not edit it.

### Build the zip

**Linux / macOS** — from inside your evidence folder, name the six files explicitly:

```bash
zip G_YourName.zip \
  G_YourName_01_Recon.png \
  G_YourName_02_Vulnerability.png \
  G_YourName_03_Demonstration.png \
  G_YourName_SessionLog.txt \
  G_YourName_Reflection.pdf \
  G_YourName_ContributionForm.pdf
```

Or, if you would rather start from the whole folder and exclude the rest:

```bash
zip -r G_YourName.zip . -x "*.md" ".gitignore" "working-files/*" ".git/*"
```

**Windows (PowerShell):**

```powershell
Compress-Archive -Path G_YourName_01_Recon.png, G_YourName_02_Vulnerability.png, G_YourName_03_Demonstration.png, G_YourName_SessionLog.txt, G_YourName_Reflection.pdf, G_YourName_ContributionForm.pdf -DestinationPath G_YourName.zip
```

**Windows (tar, built into Windows 10 and 11):**

```bat
tar -a -c -f G_YourName.zip --exclude="*.md" --exclude=".gitignore" --exclude="working-files" *
```

Before you send, open the zip and check two things: it holds exactly six files, all with your name on them, and there is no README, no `.md` and no `.gitignore` inside it.

If your laptop could not run the Metasploitable VM, your reflection and your instructor note each say where your chain ran. Send the zip anyway. An honest rehearsal log beats a missing submission, and the guide keeps mistakes in the log on purpose.
