**Installing the application on Linux is recommended over Windows due to easier installation and better performance. Nowadays, Ubuntu Desktop is user-friendly and not significantly different from Windows. Here is a guide on [How to install Ubuntu Desktop].(https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview).**
# Installation in Three Steps:

1. **Install Docker Compose following the [Official guide](https://docs.docker.com/compose/install/).**

   (In older versions of Windows, if Docker prompts you to set up Windows Subsystem for Linux 2 (WSL 2), you only need to follow steps 4 and 5, not step 6. Once these steps are completed, a system reboot is necessary for the changes to take effect.)

   For Windows systems, Docker Desktop must be manually started. You can do this by clicking the Docker Desktop icon, which allows the application to run in the background.  

   **[Screenshots for step by step guide](https://github.com/RTKlab-BYU/Proteomic-Data-Manager/wiki/Installation_screenshoots#install-docker)** 

2. **Configure the application.** After [Downloading the repository](https://github.com/RTKlab-BYU/Proteomic-Data-Manager/archive/refs/heads/master.zip), extract the file to a local folder, there are two files that need to be configured: .django_secrets.env_example and docker-compose.yml.       
    * Rename .django_secrets.env_example to .django_secrets.env (don't forget the "." in the beginning of the file name, only delete the "_example" part).
    * Configure docker-compose.yml (docker configure file, required) using any text editor(e.g., notepad, VS Code, etc.):
         * Configuring the storage locations for your data, including raw files and processed data, involves setting up to four different locations or drives. The primary storage is a required configuration, while the other three - secondary storage, remote storage, and offline storage - are optional but highly recommended to ensure redundancy.
           If the specified folders do not exist, the system may return an error. Thus, to ensure compatibility, all four drives are set to the 'C' drive in a Windows system by default. However, you can change any of these storage locations by modifying the corresponding 'source' field in the 'bind' section (**only change the 'source' field, do not alter the 'target' field**).

           The format for specifying storage locations differs based on your operating system. For Windows hosts, the format is /d/docker/primary_storage, which corresponds to the location d:/docker/primary_raw. Linux, on the other hand, uses its native format, /user/xxx/documents/primary_raw.

           You can configure up to four storage locations(primary_storage, secondary_storage, remote_storage, offline_storage) for use in the app. If you're not using all of them, you can either comment out the unused ones using "#" or point it to an empty folder (recommended for easy future expansion). The naming conventions for storage locations, such as "remote_storage," do not need to be taken literally. For instance, "remote_storage" does not necessarily have to point to a remote folder. These are merely default names and can point to any location based on your preference and requirements. [Finished example](https://github.com/RTKlab-BYU/Proteomic-Data-Manager/wiki/Installation_screenshoots#point-the-setting-in-the-configure-file-to-these-foldersdrivers)
         * (Optional, only for advanced users) Only modify other sections as needed (only for advanced users)
    * Configure .django_secrets.env(optional):
         * You have the ability to configure certain parameters used within the Django app, such as time zone, debug mode, email server, Jupyter password, among others. These parameters can be adjusted based on your specific needs. If you're not sure what to set, you can leave them as their default values, or configure them as their names suggest. It's important to ensure that any changes you make align with your system settings and operational requirements.

   **[Screenshots for step by step guide](https://github.com/RTKlab-BYU/Proteomic-Data-Manager/wiki/Installation_screenshoots#configure-the-application)** 

3. **Start the app.** After you have configured the necessary files, you can start the app by running the command "docker compose up" in the directory of the extracted folder (usually named Proteomic-Data-Manager-master). You can do this in the Command Prompt for Windows [(Guide)](https://www.digitalcitizen.life/command-prompt-how-use-basic-commands/)  or the Terminal for Mac or Linux [(Guide)](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview). If you encounter a "file exists" error, simply retrying the command usually resolves the issue.

   **[Screenshots for step by step guide](https://github.com/RTKlab-BYU/Proteomic-Data-Manager/wiki/Installation_screenshoots#start-the-application)** 

Alternatively, if you have installed Visual Studio Code or another integrated development environment (IDE) with the appropriate extensions, you can right-click the docker-compose.yml file and select "Compose Up". If you encounter any errors, refer to the [troubleshooting page](https://github.com/RTKlab-BYU/Proteomic-Data-Manager/wiki/Troubleshootings) for potential solutions and advice.


**if installed properly, you should see a screen similar to the following screenshoot.**

**What's Next?
[How to access the application](https://github.com/RTKlab-BYU/Proteomic-Data-Manager/wiki/How-to-access-the-application)**

![image](https://github.com/RTKlab-BYU/Proteomic-Data-Manager/assets/77813931/e6033288-1313-46de-be12-8a304efbc593)


