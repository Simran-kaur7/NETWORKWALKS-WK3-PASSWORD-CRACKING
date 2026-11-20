# Task 1 — Password Cracking with JTR + Johnny

**Objective:** Crack the passwords of three encrypted PDF files using John the Ripper (JTR), driven through the Johnny GUI.

## Tools Used
- **John the Ripper (JTR)** — the password-cracking engine
- **Johnny** — a GUI front-end for JTR, so attacks can be run point-and-click instead of via command line
- **[onlinehashcrack.com PDF Hash Extractor](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php)** — used to pull a crackable `$pdf$...` hash out of each locked PDF (the same format `pdf2john` produces)

---

## Step 1 — Launch Johnny and point it at John the Ripper

Johnny itself doesn't crack anything — it just drives the real John the Ripper binary. The first time you open it, it has no path configured yet, so nothing is loaded.

![Johnny on first launch](01-johnny-fresh-launch.png)

In **Settings**, I browsed to `john.exe` inside the extracted John the Ripper folder so Johnny knows which executable to call.

![Johnny Settings with John the Ripper path configured](02-johnny-settings-john-path.png)

---

## Step 2 — Extract, crack, and verify each PDF

### 🔒 PDF 1

I uploaded the locked PDF to the online hash extractor, which parsed its encryption dictionary and returned a crackable hash in `$pdf$...` format.

![PDF1 hash extraction](03-pdf1-hash-extraction.png)

I copied that hash into a plain text file, `hash1.txt`, since that's the format Johnny expects to import.

![PDF1 hash saved as hash1.txt](04-pdf1-hash1-txt-saved.png)

Back in Johnny, I used **Open password file** to load `hash1.txt`. At this point the attack hasn't started yet — 0% cracked.

![Johnny loaded with PDF1's hash](05-pdf1-johnny-loaded-hash.png)

Clicking **Start new attack** ran JTR's default wordlist attack. It found a match almost immediately: the password was `good-luck`.

![PDF1 cracked — password good-luck](06-pdf1-cracked-goodluck.png)

Finally, I opened the PDF and entered `good-luck` to confirm it unlocks — and captured the flag.

![PDF1 opened with cracked password, flag visible](07-pdf1-flag-opened.png)

> **Result:** Password = `good-luck` | Flag = `nw{cybersecurity_flag_captured_2608}`

---

### 🔒 PDF 2

Same process repeated for the second PDF — extract the hash:

![PDF2 hash extraction](08-pdf2-hash-extraction.png)

Save it as `hash2.txt`:

![PDF2 hash saved as hash2.txt](09-pdf2-hash2-txt-saved.png)

Run the attack in Johnny — this time the password was `password1`, a very common password that gets guessed almost instantly by any wordlist:

![PDF2 cracked — password password1](10-pdf2-cracked-password1.png)

Opened the PDF with the cracked password and captured the flag:

![PDF2 opened with cracked password, flag visible](11-pdf2-flag-opened.png)

> **Result:** Password = `password1` | Flag = `nw{networkwalks_persistence_jtr_270521}`

---

### 🔒 PDF 3

Extracted the hash for the third PDF:

![PDF3 hash extraction](12-pdf3-hash-extraction.png)

Saved it as `hash3.txt`:

![PDF3 hash saved as hash3.txt](13-pdf3-hash3-txt-saved.png)

This time the attack took slightly longer since the password was a keyboard-pattern password rather than a dictionary word — JTR cracked it as `1qaz2wsx`:

![PDF3 cracked — password 1qaz2wsx](14-pdf3-cracked-1qaz2wsx.png)

Opened the PDF with the cracked password and captured the final flag:

![PDF3 opened with cracked password, flag visible](15-pdf3-flag-opened.png)

> **Result:** Password = `1qaz2wsx` | Flag = `nw{networkwalks_flag_260821_1}`

---

## 📊 Summary of Results

| PDF | Cracked Password | Flag |
|---|---|---|
| My Locked PDF1.pdf | `good-luck` | `nw{cybersecurity_flag_captured_2608}` |
| My Locked PDF2.pdf | `password1` | `nw{networkwalks_persistence_jtr_270521}` |
| My Locked PDF3.pdf | `1qaz2wsx` | `nw{networkwalks_flag_260821_1}` |

## 🎓 Learning Outcome

All three passwords were cracked in well under a minute because they're all common, dictionary-style, or keyboard-pattern passwords. This is exactly what the lab is designed to show: wordlist attacks are devastatingly effective against predictable passwords, which is why strong, random, unique passwords (and multi-factor authentication) matter so much in practice.
