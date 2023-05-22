# Lab Report 3: Researching Commands
Using Find
---

1. To find file by name
```
find /path/to/search_directory -name "filename.txt"
```


- ```find ./technical -name "chapter-1.txt"```


This finds the file name "chapter-1.txt" under the technical directory. 


<img width="655" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/7e2e9d03-3ac8-42e6-9f20-ea5db6095244">


- ```find ./technical -name "Comments_on_semiannual.txt"```


This finds the file name "Comments_on_semiannual.txt" under the technical directory.


<img width="664" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/3a3b1f33-31ca-4fc5-9f40-381ca439f7d6">

---
2. To find file by type (file)
```
find /path/to/search_directory -type f
```


 ```b```       block special
 
 
 ```c```       character special
 
 
 ```d```       directory
 
 
 ```f```       regular file
 
 
 ```l```       symbolic links
 
 
 ```p```       FIFO
 
 
 ```s```       socket

- ```find ./technical/government/About_LSC -type f```


This goes from the home directory to technical to government to About_LSC directory. Then, under the About_LSC directory, they try to find the files under the ./technical/government/About_LSC directory.
<img width="668" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/9b33f095-3cd8-4c64-9d25-5d4bede687c6">

- find ./technical -type f


This goes through through the technical directory and find all the files.
<img width="623" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/9fc1f445-da79-4865-a839-ed77c317a352"><img width="667" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/a2587fab-8681-4d48-bb9d-5929fa130790">


---
3. To find file by type (directory)
```
find /path/to/search_directory -type d
```

 ```b```       block special
 
 
 ```c```       character special
 
 
 ```d```       directory
 
 
 ```f```       regular file
 
 
 ```l```       symbolic links
 
 
 ```p```       FIFO
 
 
 ```s```       socket


- ```find ./technical -type d```


This finds all the directories directly under the technical directory.


<img width="613" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/bd019845-b68c-4086-b67b-044ff3d617ea">

- ```find ./technical/government -type d```


This goes through the technical directory to the government directory. Then, it finds all the directories directly under the government directory.


<img width="650" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/844c6105-6a37-4f0c-ad7d-b8fbae3158da">


---

4. To find files based on size
```
find /path/to/search_directory -size +1M -mtime -7
```

- ```find ./technical -size +200k```


This look through all the files under the technical directory that is greater than 200 kilobytes.


<img width="602" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/dd8fbf8e-3804-4a06-9fe2-78005cd1702a">


- ```find ./technical -size -1k```  


This look through all the files under the technical directory that is less than 1 kilobytes.


<img width="582" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/fc31676e-b0b4-42f4-b3bf-81cf6a74c3a0">

5. To find files based on the amount of subdirectories there is
```
find /path/to/search_directory -maxdepth 2
```

- ```find ./technical -maxdepth 1```


This looks through the technical directory and show everything that is in the first depth, directly under the technical directory.


<img width="615" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/e13c67fe-9c46-44fe-85fc-dac792628f40">


- ```find ./technical -maxdepth 0```


This looks through the technical directory and show everything that is in the zero depth, the current directory.


<img width="603" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/cae69590-8b6e-4307-aed5-c544fccb577e">

---
Work Cited Area
- ***ChatGPT***

I ask ChatGPT 3 questions

1.give me four ways to use find in command line

<img width="645" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/dcbe1d5b-10b3-4717-81a8-3c2f3f61deeb">

2.how to use find by size

<img width="563" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/75c90644-d0f1-4aea-8e74-e04b572baf4b">

3.find criteria 

<img width="500" alt="image" src="https://github.com/JingtingL/cse15l-lab-reports/assets/89711106/3f380d6c-04d9-467a-84cb-09a2d730974c">

- ***man find from terminal***


