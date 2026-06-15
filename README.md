Q1)Create Local Repository with featureA and featureB Branches and Push to GitHub
# Create repository
mkdir MyProject
cd MyProject
git init

# Create initial commit
echo "Initial File" > README.md
git add .
git commit -m "Initial commit"

# Create featureA branch
git checkout -b featureA
echo "Feature A File 1" > featureA-file1.txt
echo "Feature A File 2" > featureA-file2.txt
git add .
git commit -m "Added files to featureA"

# Create featureB branch
git checkout main
git checkout -b featureB
echo "Feature B File 1" > featureB-file1.txt
echo "Feature B File 2" > featureB-file2.txt
git add .
git commit -m "Added files to featureB"

# Add remote repository
git remote add origin https://github.com/username/repository.git

# Push branches
git push -u origin main
git push -u origin featureA
git push -u origin featureB
--------------------------
2. Clone Repository → Create dev Branch → Modify File → Merge into Main → Push
# Clone repository
git clone https://github.com/username/repository.git

# Enter repository
cd repository

# Create dev branch
git checkout -b dev

# Modify file
echo "New Content" >> file.txt

# Commit changes
git add file.txt
git commit -m "Updated file"

# Switch to main
git checkout main

# Merge dev into main
git merge dev

# Push main branch
git push origin main
------------------------------
3. Resolve Merge Conflict in HTML File
a. Identify Conflicting Files
git status
b. Edit File and Resolve Conflict

Conflict Example:

<<<<<<< HEAD
<h1>Main Branch</h1>
=======
<h1>Feature Branch</h1>
>>>>>>> feature

Edit to:

<h1>Final Version</h1>

Then:

git add index.html
c. Finalize Merge
git commit -m "Resolved merge conflict"
------------------------------------
4. Clone Repository → Make Changes → Merge → Commit to New Branch → Push
# Clone repository
git clone https://github.com/username/repository.git

cd repository

# Create new branch
git checkout -b new-feature

# Make changes
echo "New Feature" >> file.txt

# Commit changes
git add .
git commit -m "Added new feature"

# Merge latest main changes
git checkout main
git pull origin main

git checkout new-feature
git merge main

# Push new branch
git push -u origin new-feature
---------------------------------------------
5. Clone Repository → Create dev Branch → Modify File → Merge into Main → Push
git clone https://github.com/username/repository.git

cd repository

git checkout -b dev

echo "Updated Content" >> file.txt

git add .
git commit -m "Updated file in dev"

git checkout main

git merge dev

git push origin main
----------------------------------
6. Create Local Repository project-alpha
a. Create Repository
mkdir project-alpha
cd project-alpha
git init
b. Add Files
echo "Meeting Agenda" > notes.txt
type nul > data.csv
c. Commit Files
git add .
git commit -m "Initial project setup"
d. Create experiment Branch and Add test.py
git checkout -b experiment

echo print("Hello") > test.py

git add test.py
git commit -m "Experimental feature"
