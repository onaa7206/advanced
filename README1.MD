VSEC-1





1)create folder (ds-project)


go in folder open git bash:


type:


git config --global user.name "Aarya7206g"


git config --global user.email "aarya.gaikwad.aids.2023@vpkbiet.org"


git init


2)create repo(ds-project) in github:


copy repo link then in git bash:


 git remote add origin https://github.com/Aarya7206g/ds-project.git

 
3)create file using following in gitbash:


touch program1.py


open that file:


code program1.py


4)type multiplication code in it:


ex:num = int(input("Enter a number: "))

for i in range(1, 11):

 
 print(num, "x", i, "=", num * i)


save 


5)on bash:


git add program1.py


git commit -m "Initial commit"


git branch -M main ##(created branch)


git push -u origin main


6)make some changes in prog and save and type same above commands but instead of "initial commit" type another msg "updated code"


7)create other program:


git bash:


touch program2.py


code program2.py


write greatest no. code:


a = int(input("Enter first number: "))


b = int(input("Enter second number: "))

if a > b:


print("Greatest is:", a)


else:


print("Greatest is:", b)


    
8)bash:


git checkout -b GIT-EXAM


9)bash:


git add program2.py


git commit -m "Added greatest number program"


git push origin GIT-EXAM


On branch GIT-EXAM


now see in github repo for files
