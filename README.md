# GDG Recruitments 2026: Task 1A - Forensics Challenge
**Objective:** Recover three hidden flag fragments to assemble the final key: `Gdg{part1_part2_part3}`.

---

## 🧩 Part 1: Git Forensics
* **Method:** Analyzed the repository's hidden history using `git reflog`.
* **Discovery:** Identified a suspicious commit hash with the message: `"(oops, committed secrets!)"`.
* **Action:** Checked out the specific commit to recover a hidden configuration file.
* **Fragment 1:** `gdg{sw1ss_`

## 🖼️ Part 2: Image Forensics (Steganography)
* **Method:** Used `binwalk -e` on `heheheha.png` to extract embedded data.
* **Discovery:** Found a Zlib compressed stream at offset 29.
* **Action:** Due to header corruption, I used the `strings` utility to scan the binary blob for human-readable flag fragments.
* **Fragment 2:** `aLs9aA_`

## 📱 Part 3: QR Code Mass-Automation
* **Method:** Faced with 3,000 unique QR code images, I developed a Bash automation script.
* **Action:** Used `zbarimg` in a loop to scan every image and pipe the output to a report.
* **Processing:** Filtered the results with `grep -v` and decoded the final Base64 string.
* **Automation Script:**
    ```bash
    #!/bin/bash
    for file in *.png; do
        zbarimg "$file" >> scanreport.txt
    done
    ```
* **Fragment 3:** `gg1ol}`

---

## 🏁 Final Assembled Flag
**Flag:** `gdg{sw1ss_aLs9aA_gg1ol}`
