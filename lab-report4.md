# Lab Report 4
Steps 4-9
---
4. **Step 4: Log into ieng6**
- Type `ssh cs15lsp23co@ieng6.ucsd.edu`
- Enter your password

This is what it should look like:

<img width="500" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/c51e2f9f-86e9-4787-94b3-b31cd2af64c3">

---

5. **Step 5: Clone your fork of the repository from your Github account**
- Go to [https://github.com/ucsd-cse15l-s23/lab7](https://github.com/ucsd-cse15l-s23/lab7)

<img width="500" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/ac5af1eb-707b-4c16-9b43-f075e1d00428">

- Click fork and Create fork

<img width="600" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/2ce8a593-bc9f-42f9-9643-4b072a30d262">

- Type `git clone https://github.com/JingtingL/lab7.git` 

**End Result of Step 5 should look like this**

<img width="613" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/090eb7a8-ab5b-4808-a730-0e6f7d873f77">

---

6. **Step 6: Run the tests, demonstrating that they fail**
- Type `cd lab7`
- Type `bash test.sh`

<img width="632" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/138a2b32-8337-4dae-aaed-ff77c832deec">

---

7. **Step 7: Edit the code file to fix the failing test**
- Type `vim ListExamples.java`

- Go to the first line of the file in vim, Type `j` 43 times
- Highlight the 1 in `index1` of the line

<img width="449" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/918eb9aa-7299-415e-b97a-5ea7b719f474">

- Type `x` once to delete the 1

<img width="449" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/1c7d27a2-a958-4449-9d13-34c13854e8e5">

- Type `i` to go to insert mode
- Type `2` to get the output below

<img width="425" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/5874d471-a4cc-4917-ab70-8c2380ec5f8e">

- Press the `<esc>` button to go to normal mode
- Type `:wq` to save the file and quit vim

**At the end of Step 7, your output should look like this**

<img width="596" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/98bf34d9-c629-4b9d-9505-ce9e76e61cc3">

---

8. **Step 8: Run the tests, demonstrating that they now succeed**
- Type `bash test.sh`

**At te end of Step 8, your output should like this**

<img width="542" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/8c8aac76-219a-4b19-9064-76681c5ef1d4">

---

9. Step 9
