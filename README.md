# TexStudio-GIT
Notas sobre el control de versiones en TexStudio usando GIT

# Configuration Steps
1. Open your main *.tex file in TeXstudio and type in the terminal (Tools_Open Terminal) the following two lines:  

   line | description
   ----------------------------------|---------------------------------
   git init | This creates a GIT repository  
   git add filename1.tex filename2.tex... | This loads the TEX files to be monitored

2. Create a batch file in the directory of your main *.tex file
3. Open the batch file and add the following line: git commit -am "autosave %date%-%time:~0,8%". This will commit all changes made (-a switch) and set the commit message to e.g. autosave 2015-08-17-09:34:05
4. Add a custom command in TeXstudio that executes your batch script (Options_Configure TeXstudio_Build_User Commands)  
   gitcommit:gitcommit      cmd "/c main.bat"
5. Add your custom command to the list of commands for compilation (Options_Configure TeXstudio_Build_Build & View)  
   txs:///compile | txs:///view | txs:///gitcommit
6. After the next compilation of the document, the following message will appear in the message log:  
   git commit -am "autosave 2015-08-17-09:34:05"
7. Additionally, the batch file could be modified accordingly to push the changes directly to the remote repository via git push (pending).
