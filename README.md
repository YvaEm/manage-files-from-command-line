<p align="center">
  
![image](https://github.com/user-attachments/assets/2b5498ff-27e0-4018-bbda-a1d319aee2bf)

<h1>Manage files from the command line</h1>
This Lab demonstrates how to Manage, Diplay specific number of lines and Edit files all from the Linux Command Line.<br />



<h2>Environments and Technologies Used</h2>

- Redhat Linux 
<h2>Operating Systems Used </h2>

- Linux

<h2>High-Level Deployment and Configuration Steps</h2>

Manage files from the command line.

Display a specific number of lines from text files and redirect the output to another file.

Edit text files.

 

<h2>Deployment and Configuration Steps</h2>


<p>
Login to serverb as the student user.
  
  ```
  ssh student@serverb
  ```

![image](https://github.com/user-attachments/assets/279989c5-b5d5-41ec-bb7c-4a9232f2ef04)




</p>
<br />


<p>
Create the /home/student/grading directory

```  
  mkdir -p /home/student/grading
```

![image](https://github.com/user-attachments/assets/679a593b-e639-41d2-b33f-1044476b294e)

</p>
<br />


<p>
Create three empty files called grade1, grade2, and grade3 in  the /home/student/grading directory

  ```
  touch grading/grade{1..3}
  ls grading
  ```

![image](https://github.com/user-attachments/assets/780ea07f-1843-46e9-beec-5ff3d341c262)



<br />


<p>
Capture the First 5 lines of the /home/student/bin/manage file int eh /home/student/grading/review.txt

  ```
  head -5 /home/student/bin/manage > grading/review.txt
  cat grading/review.txt
```
![image](https://github.com/user-attachments/assets/6abbba50-3400-4b43-b9eb-2c5dcd7b17e4)



</p>
<br />


<p>
Append the last 3 lines of the /home/student/bin/manage file to the /home/student/grading/review.txt file
  
Do not overwrite any existing text in the /home/student/grading/review.txt file.

```  
  tail -3 /home/student/bin/manage >> lsgrading/review.txt
  cat grading/review.txt
```
I forgot to add a second greater than sign(>) meaning I wrote over any text in the file. 

I went back and re-did the head command and tail commands properly 
![image](https://github.com/user-attachments/assets/fc6d2e9a-aff5-4ba1-9e36-77b34a804af0)

  
</p>
<br />


<p>
Copy the /home/student/grading/review.txt file to the /home/student/grading/review-copy.txt file

  ```
  cp grading/review.txt  grading/review-copy.txt
```
![image](https://github.com/user-attachments/assets/4efdcf65-6d21-4390-889e-a2e5ce377097)



</p>
<br />


<p>
Edit the /home/student/grading/review-copy.txt file so that the Test JJ line appears twice.
Edit the /home/student/grading/review-copy.txt file to remove the Test HH line.
Edit the /home/student/grading/review-copy.txt file so that a line with A new line exists between the Test BB line and the Test CC line.

```
  vim grading/review-copy.txt
  cat grading/review-copy.txt
```
![image](https://github.com/user-attachments/assets/0bcb0864-e6cb-4444-8df8-0253f0c07b57)
![image](https://github.com/user-attachments/assets/a5956528-1984-408a-9fa2-e5b44cbcc434)

  
<br />

<p>
Create the /home/student/hardcopy hard link to the /home/student/grading/grade1 file. You must create the hard link after completing the earlier step to create the /home/student/grading/grade1 file.

```  
  ln grading/grade1 hardcopy</p>
```
![image](https://github.com/user-attachments/assets/ced53108-d2cb-48e7-8b1c-e05260d1a879)

  
<br />


<p>
Create the /home/student/softcopy symbolic link to the /home/student/grading/grade2 file.\
  
  ```
  ln -s grading/grade2 softcopy
  ```
![image](https://github.com/user-attachments/assets/5d7d9f8d-fbee-4776-873c-c6eb5326c926)


<br />


<p>
Save the output of a command that lists the contents of the /boot directory to the /home/student/grading/longlisting.txt file. The output should be a "long listing" that includes file permissions, owner and group owner, size, and modification date of each file. The output should omit hidden
  
```
  ls -l /boot > grading/longlisting.txt
```

I forgot to do the /boot argurment in the ls -l command causing me to fail.

Went back into the server and properly exucuted the command.
![image](https://github.com/user-attachments/assets/5396d880-84d4-4296-b4b3-e0f33e587821)
![image](https://github.com/user-attachments/assets/334e199b-3e90-4fb9-ac5c-7446e76adac5)
![image](https://github.com/user-attachments/assets/b355f8be-7260-45d7-ae0b-d0be0169c2bf)






<br />



