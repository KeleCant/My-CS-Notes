### HTML File Path
Proteomic-Data-Manager/web/file_manager/templates/filemanager
### CSS File Path
Proteomic-Data-Manager/web/static/
  - to me it seems that this program does not incorperate custome Css files but rather pules from a library of CSS feutures.
### JavaScript
- I dont know enough about JavaScript to make a jusgment but it seems again that it is run with a library of java commands in mind.

 ### Passwords

 admin/proteomicsdatamanager

search_worker/searchadmin

JUPTER_PASSWORD ='itsasecret'

### Notes

  - In my experimenting with MS Connect I attempted to run a data file and determined that the program is useless without installing programs.
  - I attempted to install a data reading program but got sidetracked trying to figure it out.
  - I found a tutorial that will teach me how to move forward from here.
  - In this reserch I also documented there comunity pages, I think it is interesting that these community pages have 1 active community member. With this in mind I think two things need to be considered for the future, one advertizing so others can use and develop the app. Two, I need to find out what this product has that others don't that make it stand out and make it unique from other programs.

### 2/12/2024
- Today I picked up where I left off and looked into uploading raw type files to the websight. What I discoverd is that it isnt too bad. First you need to go to the help bar, then download the raw file uploader. from there you just need to incert your file inot the uploader, change a default setting and you have your data on the websight.
- I do think that the raw file uploader seems like a hassle in itself, so if there is a way to upload the files that would be way easier then I should look into it. If we want this to go public and go but then it needs to be user friendly. THe raw file uploader is programed in C# so I will have to learn a compleatly new language. I do think that there should be either an uploader on the websight or a tuttorial on the websight, one of these should be implimented in order to maxamize efficiency.
- After reading through the raw file uploader code it apears that I do not understand how it functions at all.
- I went through and installed all of the avaleble apps. one in each catagory did not work and Chat GTP asked for an admin api key, so I believe some work needs to be done on those. 

### 2/13/2024
- Chat GTP does not work
- DDA DIA WWA error 404

- Met with Lavander, learned that I need to present march 21st. Met with Xiao Fein, We discused that I will present the instalation process. My Job is to read through and study all of the program and search for spelling errors. It is also to improve the instalation process to make it smoother.
- Talked to him about removing the uploader and he instructed me that it is that way becuse of how .raw files are recieved.
- Talked about chat GTP - It requires a payed subscription.
- DDA DIA WWA does not work yet, he explained that to me.

- Now I will look for errors on the Raw Uploader
![image](https://github.com/KeleCant/My-CS-Notes/assets/94769317/1fa1dbb6-eb33-487e-ba93-82d9610f3084)
- Replace "Folder to Monitor or Upload" to "Folder Path"
- Replace "File to upload" to "File Path"
- "Open full log" to "View Log"
![image](https://github.com/KeleCant/My-CS-Notes/assets/94769317/5291040a-4073-4f2b-88b1-b402406b43ff)
- I dont know what this page is for. it could be helpful to have default settings or
- What is that question mark doing in there?

### 2/15/2024
- Today's plan.
    1. Read through websight and record any errors
         -all i see are potential cap errors but I think they are intentional
    2. uninstall and reinstall the program.
        - I deleted all the files but a django managment file refused to delete. I did the reinstall process and found no solution to my problem. I cannot get the websight working now.
        - after unistalling the docker program and reinstalling it then reinstalling MS connect, then i was able to get the program working.
    4. review wiki page
    5. review form page
 - I do believe that the app center needs a little work. for a new user it can be confusing trying to download apps for the first time


### 2/28/2024
- Total task - refine the material
- have parker install
- someone else - have someone with limited expeiance test tutorial
- Get familiar with usage
- less priorety 
- C# bug fixes
- Merg all commits for MS Connect
- Pull request

- learn how to automaticl upload files -- upload that asap
- work on MS Connect functionality wiki pages

### Things to do
- [L] Prepare presentation for March 21st
- [L] Raw Filer Uploader C# edits
- [H] Betta testing
    - 1. Have parker trial download the program
    - 2. Have an undergrad trial download the program
- [H] Proteiomics Data Manager Wiki page
    - learn functionality of the page
    - Adding
    - Clean up Side Bar
        - How to install
        - systemsettings
        - 
- [H] Raw File uploader Wiki page
    - Auto uploader
    - File lock checker tutorial
    - Metadata tutorial
    - Finish "How to set up custom data types page
    - review everything
- Pages that need to be creates
    - Proteomics_Data_Processor GitHub Wiki
    - Processing Node and Visulization Node wiki
    - Jupiter Notebook python and R
    - Rest API






 3/5/2024
 After spending many hours trying to get my docker to work I believe we have found the problem.
 When I deleter the files in my primary storage it allowed the docer to compile and run.
 Now I am going through to see which file is causing the error exactly.
 0. Test 0: Delete all files in Docker/Storage and run
 1. Test 1: Reinstall those prevously installed files to make sure that the problem is isolated. Result: The servers are continously restarting. Problem isolated.
 2. Test 2: To save time and I believe the problem is located elsewhere, I removed the files log, pki, rawfiles, systemfiles and will run "docker compose up" Result: Removing these files causes the program to run normaly
 3. Test 3: redoing test 2 but reversed. Removed Database_backup and JupiterNotebook. Running log, pki, rawfiles, and systemfiles. Result, servers enter restarting cycle
 4. Test 4: removing system settings and running again. The program runs normals. I need to run one more test to make sure its this file causing the problem
 5. Test 5: Run with only the systemsettings file Result: server enters restart cycle

 7. Test 6: Removing presets Results: Restart Cycle starts
 8. Test 7: remove chatgtp_chat, codes, and DIANN Results: Restart Cycle starts
 9. Test 8: remove fragpipe19, images, maxquant20 Result: Restart cycle starts
 10. Test 9: Remove pd2-5, pd3-0, schedule.pki Result: Server runs Normal
 11. Test 10: Add schedule.pki Result: Restart cycle starts
 12. Test 11: Add pd2-5, pd3-0 remove schedule.pki Result Server Runs Normal

After further review it apears that it is an error in the HTML that is crashing the server. In the code the setting is 1-6 but the HTML allows for 1-7. If you select 7 the entire server will crash becuse it is out of range. Curently fixing the HTML
