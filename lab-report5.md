# Lab Report 5

## Part 1 Debugging Scenario

1. The original post from a student with Symptom and Description of a guess
<img width="675" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/554c36b9-f752-48df-b4bd-ab1030b10643">

<img width="594" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/455441cd-d5c7-4f44-bf38-89a761c760f4">

<img width="602" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/df7eae69-cbfe-48b6-bfdb-525f54c04770">

<img width="619" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/e89aaf36-d04e-43c4-bbeb-57e893aa5f71">

<img width="655" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/892e0324-5e56-432d-88ce-ce33f4c28ebc">


```
TA Response: This is an very interesting error. Please know the path is a String, so please quote the first line of grade.sh. 
```

2. The student change line 1 of grade.sh to be 


```CPATH= '.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'``` and still experiences a bug in her code.

<img width="991" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/a45f9892-feca-4f39-8439-33b512bfcf05">

She then remove the space in front of the ```=``` in  line 1 of grade.sh. And the code is fixed.


```CPATH= '.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'``` and still experiences a bug in her code.

The bug is there is a space  and there is no quote.

## Part 2 Reflection
In the second half of the quarter, I learned how to use vim and bash file to make working with the terminal easier for me. With vim, I can edit files in the terminal instead of naviating to VS Code. Also ther are also lots of shortcuts with vim, which makes editing files much easier. With bash, I can put a bunch of bash commands in a single file and run it all at once, which I believe is very convenient. 
