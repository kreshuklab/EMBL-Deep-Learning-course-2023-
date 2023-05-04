# EMBL Deep Learning course exercises and materials

## Schedule:

TODO

## Set-up:

We will use on-premise EMBL resources for the course. You can also use google colab to run any of the notebooks.

## BAND

We will use BAND desktops, cloud based virtual desktops provided by EMBL to work on the exercises for Webinar 2 & 3 and during the course itself. 
These BAND desktops are open resources provided by EMBL as part of EOSCLife. For the duration of the course they will be reserved for the course participants.

### Using BAND

- Go to [band.embl.de](https://band.embl.de/#/eosc-landingpage) and click `LOGIN`.
- Use your Google account to log in. If you login for the first time, you will need to wait a few minutes to obtain a confirmation e-mail. Check out [the BAND user guide](https://docs.google.com/document/d/1TZBUsNIciGMH_g4aFj2Lu_upISxh5TV9FBMrvNDWmc8/edit) or [the BAND video tutorial](https://drive.google.com/file/d/11pbF70auGyWF-1ir2XUGM8fgiY7ETxP8/view) for more information.
- This will open the `Launch Desktops` page
    - Select a suitable configuration in `Desktop configuration`, see example in the screenshot below.
    - Click `LAUNCH` and then `yes` in the prompt
    - Click `GO TO DESKTOP` in `Running desktops`
- This will open the virtual desktop in a new tab.
    - Note that for some users starting the first virtual desktop fail and display a `CONNECTION ERROR`. If that happens for you, just terminate the desktop and start a new one; that should fix the issue.  
- You can now use this desktop to use pre-installed software or install new software
- In BAND you have write access to your directories in `/home` and on `/scratch`. `/home` has very limited space, therefore you should store all your data on `/scratch`.  
You can create your directory on `/scratch` like this:  
`mkdir /scratch/your_name`  
Data that you save on `/scratch` is persistent between sessions and will be stored for 3 months.  
- The environment for the webinar exercises is already preinstalled via jupyterLab, you can access it via `Applications->Programming->DL Course`
- This will open jupyter lab. You can test it e.g. with the notebooks at https://github.com/constantinpape/dl-teaching-resources

![band2](https://user-images.githubusercontent.com/4263537/134918656-884239a9-2951-4adb-8fad-8c4c883a65ce.png)

### More information

- Users can install software or download data into their directory on `/scratch`, which persists in between sessions.
- The required software and environments can be pre-installed (see example for `DL Course` environment above) so course participants don't need to set up everything on their own.
- Traning data or other large data-sets can be shared via the EMBL S3 data storage, which can be accessed via `Applications->Data Access->Mount EMBL S3 Bucket`

### Downloading the exercises to BAND

- Open the terminal (e.g. via small terminal system in the top toolbar)
- Go to your directory on `/scratch`: `cd /scratch/your_name`
- clone this repository via `git clone https://github.com/kreshuklab/teaching-dl-course-2022.git`
- Now you can navigate to the folders with exercises in the jupyter environment to run the exercises
- To update the repository, e.g. to download new exercises, open the terminal again and
    - Go into the directory via `cd teaching-dl-course-2022.git` (or some other filepath if you did not directly clone it to your home)
    - update the repository via `git pull origin main`

### Enabling copy paste in BAND

In many browsers copy-and-paste between your system and BAND does not work by default. You can however copy-and-paste into an intermediate menu and then copy-and-paste into/from band (copy to band explained below, pasting from BAND similarly):
- copy text on your computer
- go to the BAND desktop, press `ctrl+shift+alt`
- this will open a menu; now paste the copied text into the menu (`ctrl+v`)
- copy the text in the menu (`ctrl+c`)
- close the menu again via `ctrl+shift+alt`
- now you can copy the text into BAND

If you need to copy-and-paste a lot of text and the above procedure is incovenient for you, you can also try to activate direct copy-and-paste in your browser:
- For Chrome users:
    - Open the Google Chrome browser.
    - Type the following text in the address bar: chrome://flags#shared-clipboard-receiver.
    - Select Enabled from the drop-down list next to the Enable receiver device to handle the shared clipboard feature option.
    - Similarly, enable the flag chrome://flags#shared-clipboard-ui named Enable shared clipboard feature signals to be handled.
    - Finally, enable the flag Sync Clipboard service accessible by the address chrome://flags#sync-clipboard-service
    - Restart Chrome
- For Firefox users:
    - Open a new firefox tab
    - In the URL field, type about:config and press enter to open the config page.
    - On the config page, search "Clipboard"
    - Set the following properties to true:  
    `dom.events.testing.asyncClipboard` 
    `dom.events.asyncClipboard.readText`  
    `dom.events.asyncClipboard.clipboardItem`  
    - Delete firefox cookies
    - Restart browser


## Setting up an environment on your own machine

We also provide python environments that are compatible with the course material:
- `environments/pytorch` contains the pytorch environment files (one for setting up an environment with GPU support, the other for setting up a CPU-only environment)
- `environments/keras` contains the keras environment file

You can install one of these environments with conda:
```
conda env create -f </path/to/<ENV-FILE-NAME>.yaml>
```
and then activate it via
```
conda activate <ENV-NAME>
```
If you are not familiar with conda, please refer to the [conda tutorials](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html).

## Uploading data to BAND

To upload data to BAND and share it with other course participants we use the EMBL S3 storage. In order to upload data to it:
- Go to [https://s3.embl.de/](https://s3.embl.de/)
- Log in with the credentials (available on the eCampus forum)
- Select `Buckets` in the `MINIO CONSOLE` menu
- Click on `Browse` for the `dl-course-2022` bucket
- You can now see all the data that has been uploaded already
- In the top right select `Upload file` to upload a single file or `Upload folder` to upload a folder, then select the file/folder on your file system.
- After the upload has finished you should see the new file(s) listed in the `dl-course-2022` bucket.

To access the data in the `dl-course-2022` bucket in BAND:
- Select `Applications->Data Access->Mount EMBL S3 Bucket`
- In the menu that opens enter the same credentials as before. `Access Key` is the same as the username and `Secret Key` the same as the password. Enter `dl-course-2022` for the bucket name.
- This will open a folder with the contents of the bucket that can be accessed normally through the filesystem. It is available in your home directory as `dl-course-2022`.

Note tha the data you upload will be accessible to all other participants and trainers.
Plese do not share the data another participant has uploaded without their consent.
