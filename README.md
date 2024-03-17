# githubnotes
-> Git/Github ---> it is source code management tool which helps you to manage the application code.
-> Git is local repository which is on you local machine.
-> Github is centralised repository were you need to login using username/passwd.
-> In github we can fork or import the code from other github
        for importing entire repository we use import option
        for copiying specific branch of the repository we use fork option

-> git init -> which helps to convert normal directory to git directory.(which initilise the git congiguration).

-> Git clone -> were we can download entire repository from github to local git
     git clone <github url>   (url -> github repo url)
     
     cd <reponame>  -> go inside directory
     
     vi filename    -> to create new file (esc->shift:->wq)

     LL            -> List
     
     git add .      -> . indicates all files
     git commit -m "message" -> (-m is message)
     git push origin branchname  ->push code to github.
     
     git status  -> to see the status before and after command exection for both add&commit.

     git pull origin branchname  ->pull code into local git for latest change

-> git branching ---> Branching will helps developers to work parallely or samintaniously with out any dependency on each other.
         -> when we create any branch we get a default branch called "MAIN"
         Below are the branches were developers create depends on there project
             Stage  1) feature -> were developer creat and work on there code individually
             Stage  2) develop/dev/developement-> In this all developer code will merge and quality test happen 
             Stage  3) main ->were it contains final code application
             Stage  4) release -> code releasing to customer
             
         

     git branch <bname> --> it will create branch 
     git checkout <bname>  -> switch from one to another branch
                Above two (OR) below one (same)
     git checkout -b <bname>  -> create and switch to that branch
     
     git branch -d <bname>    -> delete branch (-d delete)
     git branch    -> list the branches which are on local git
     git branch -a  -> it will list branches from both git and github. (-a   all branches)

-> git log  --> commit history display
   git log --oneline  shows commit history with less content

-> git diff <bname> <bname>     -> it will show diff b/w two branches
   git diff <commitid> <commitid>  -> it will show diff b/w two commit id's
   git show <commitid>   -> to see details info for commit id   

-> git merge --> combine two diff branches into single branch.
                  --> github->pullrequest->create pullrequest->merge request
   git checkout main
   git merge <main> <test>    -> it is merging test to main branch.  

-> git stash  --> to store current working directory temporarly 
            git stash      -> save the current work dir to stash
            git stash list -> show the list of saved items
            git stash apply -> to get back the save curent dir
            git stash drop  -> delete the saved items from stash

-> .gitignore  --> .gitignore file will helps to skip/avoid the unwanted files while pushing into github.
    vi .girignore --> *.log

-> git reset --> to undo the changes/// -> move from current state to previous state.

   git reset <filename> 
