# Bandit Notes


## 0-1: 
  - steps: ls the readme
  - goal: Basic directory navigation and reading files 
  - password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
  
## 1-2: 
  - steps: used cat./- to read a file begining with a dash
  - goal: files starting with a dash must be referenced using ./
  - password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
  
## 2-3: 
  - steps: This level was confusing. used cat ./- for the dashes(but only 1 dash) and \ for spaces
  - goal: accessing files starting with spaces need a \
  - password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
  
## 3-4: 
  - steps: used the find command and then cat
  - goal: use find to locate hidden files/directories
  - password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
  
## 4-5: 
  - steps: ls then cat./- editing the filenames until found
  - goal: use ls to identify and find hidden filenmaes
  - password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
  
## 5-6: 
  - steps: used the find -executable command to find files that are executable(deadend), used the find . -type f -size 1033c to find which file fit the criteria of 1033 bytes and found it in file 2. 
  goal: use find command to filter by specifc file size
  password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
  
## 6-7: 
  - steps: i used this command to find out ownership which was root root: (1st = user and 2nd = group) ls -ld. Then i went to root directory and used the find command to look for file with 33 bytes and got a list and looked for a file with bandit7 and cat commanded it.
  - goal: identify ownership of files and using find command
  - password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
  
## 7-8: 
  - steps: I cat commanded the data.txt file and looked for millionith
  - goal: locating file with specific text
  - password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
  
## 8-9: 
  - steps: I used sort to find groups of passwords and then used uniq -u to find the unique. 
  - goal: use sort and uniq to spot unique lines
  - password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
  
## 9-10: 
  - steps: I used the string [file] command and found the line that was preceded with = signs
  - goals: use strings to extract readable text 
  - password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
  
## 10-11: 
  - steps: I used the base64 [filename] to get the base64 encoded string and then used base64 -d [filename] to decode the string
  - goal: decode base64 string
  - password:dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
  
## 11-12: 
  - steps: I cat commanded the file and got a string and then I used the rot13 command, which essientially rotates each letter 13 positions in the alphabet(lower and upper case). The rot13 uses the tr command: tr 'A-Za-z' 'N-ZA-Mn-za-m' <<< '[file contents]'
  - goal: use tr which applies ROT13 
  - password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
  

  


