# NOTICE: the release is used as archive.
 # Note: release is only for archiving.
 Please read the descriptions of settings before raising an issue. Please read the descriptions of all setting items in the settings, and you don’t need to ask some questions.

 # Deploy to Heroku
 Official: https://heroku.com
 Demo: https://herooneindex.herokuapp.com/

 How to Install: Click the button [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com  /qkqpttgf/OneManager-php) to Deploy a new app, or create an app then deploy via connect to your github fork.


 # Deploy to Glitch
 Official: https://glitch.com/
 Demo: https://onemanager.glitch.me/

 How to Install: New Project -> Import form Github -> paste "https://github.com/qkqpttgf/OneManager-php", after done, Show -> In a New Window.


 # Deploy to Tencent Serverless Cloud Function (SCF Tencent Serverless Cloud Function)
 Official: https://cloud.tencent.com/product/scf
 DEMO: None
 Note: SCF has new restrictions. The overall maximum environment variable is 4KB, so you can add up to 4 disks.

 How to Install:
 1. Enter the function service, select the region above, and then click New.
 2. Enter the function name, select the template function, enter onedrive in the fuzzy search, any case, select the one [Get onedrive information.....], click Next, do not move in the code interface, just click Finish.
 3. Click on Trigger Management, create a trigger, change the trigger method to API Gateway trigger, tick Enable integrated response below, and submit.
 4. You can see an access path in the trigger management, visit it, and start the installation.

 (Key: check integrated response)
  
 When adding a network disk, SCF may not be able to respond and do not jump to Microsoft, causing the addition to fail. Please do not delete this disk, just add a disk with the same label again.


 # Deploy to Huawei cloud Function Graph (FG Huawei cloud function workflow)
 Official: https://console.huaweicloud.com/functiongraph/
 DEMO: None
 Note: In FG, the overall size of environment variables is 2KB, so at most 2 disks (one onedrive and one aliyundrive) can be added.

 How to Install:
   1. In the function list, click on the right to create a function
   2. Enter the name, select the runtime language as PHP7.3, click Upload ZIP file, select the file, and click the create function on the right (the ZIP file here cannot be directly used as the ZIP file downloaded from Github. After decompressing it,  After removing the outer folder, compress it to ZIP.)
   3. Create trigger: select API gateway, select None for security authentication, change backend timeout (milliseconds) from 5000 to 30000, create a group above, and other little by little
   4. Visit the url given by the trigger and start the installation
   5. Click the trigger name on the trigger interface, jump to the API gateway management, more URLs on the right, you can add a custom domain name, after customizing the domain name, you still need xxxx.com/function name to access, click the edit above, the first  1 page does not need to be changed, click Next, request Path to be changed to /, note that the matching mode is prefix matching, Method is ANY, and then no need to click Next, click Finish now, and then go to publish to take effect


 # Deploy to Aliyun Function Compute (FC Aliyun Function Compute)
 Official: https://fc.console.aliyun.com/
 DEMO: None

 How to Install:
   1. New function - HTTP function
   2. Choose php7.2 for operating environment
   3. Select anonymous as the trigger authentication method. In the request method, click GET and then POST. There are these 2 in the final box.
   4. Upload the code
   5. Click in the trigger, find the configuration custom domain name, click Go, create, fill in /* in the path, and other drop-down options.
   6. Visit your domain name and start the installation


 # Deploy to Baidu Cloud Function Compute (CFC Baidu Cloud Function Compute)
 Official: https://console.bce.baidu.com/cfc/#/cfc/functions
 DEMO: None
 The custom domain name needs to use an API gateway separately and file it.

 How to Install:
   1. In the function list, click Create function
   2. Change the creation method to a blank function, click Next
   3. Enter the name, select PHP7.2 when running, and click Next
   4. Trigger: drop down to select HTTP trigger, fill in URL path /{filepath+}, select all HTTP methods, authentication: no verification, click submit
   5. Enter the code editing page, change the edit type to upload the function ZIP package, and select the file (Zip file here cannot be directly used as the ZIP file downloaded from Github. After decompressing it, remove the outer folder and then compress it to ZIP  .),Start upload  
   6. Click the trigger on the right, copy and visit the provided url to start the installation


 # Deploy to Virtual Private Server (VPS or space)
 DEMO: None
 How to Install:
     1.Start web service on your server (httpd or other), make sure you can visit it.
     Start the web server and make sure you can access it.
     2.Make the rewrite works, the rule is in .htaccess file, make sure any query redirect to index.php.
     Turn on the pseudo-static (rewrite) function. The rules are in the .htaccess file and ngnix is ​​copied from it. Our goal is to let index.php handle whatever is accessed.
     3.Upload code.
     Upload the code.
     4.Change the file .data/config.php can be read&write (666 is suggested).
     To make the .data/config.php file in the code readable and writable by the web identity, chmod 666 .data/config.php is recommended.
     5.View the website in chrome or other.
     Visit in the browser.


 # Features
 When downloading files, the program produce a direct url, visitor download files from MS OFFICE via the direct url, the server expend a few bandwidth in produce.
 When downloading, the program parses out the direct link, and the browser downloads the file directly from the Microsoft Onedrive server. The server only consumes a small amount of traffic for communicating with Microsoft.
 When uploading files, the program produce a direct url, visitor upload files to MS OFFICE via the direct url, the server expend a few bandwidth in produce.
 When uploading, the upload url is generated by the program, and the browser directly uploads the file to this url of Microsoft Onedrive, and the server only consumes a small amount of traffic to communicate with Microsoft.
 The XXX_path in setting is the path in Onedrive, not in url, program will find the path in Onedrive.
 The XXX_path in the settings is the path in Onedrive, not in your url. The program will go to your Onedrive to find this path.
 LOGO ICON: put your'favicon.ico' in the path you showed, make sure xxxxx.com/favicon.ico can be visited.
 Website icon: Put the favicon.ico file in the directory you want to display, and make sure that xxxxx.com/favicon.ico can be accessed.
 Program will show content of'readme.md' &'head.md'.
 The contents of the head.md and readme.md files can be displayed in the file list.
 guest up path, is a folder that the guest can upload files, but can not be list (exclude admin).
 Visitors upload directory (also called picture bed directory), is to designate a directory, so that visitors can upload files, no limitation on format, no limitation on size.  The contents of this directory are not listed (unless administrative login).
 If there is'index.html' file, program will only show the content of'index.html', not list the files.
 If there is an index.html file in the directory, only the html file will be output and the program frame will not be displayed.
 Click'EditTime' or'Size', the list will sort by time or size, Click'File' can resume sort.
 Click "Time", "Size", you can sort the display, click "File" to restore the original.

 # Functional files
 ### favicon.ico
 put it in the showing home folder of FIRST disk (maybe not root of onedrive). Put it in the showing directory of the first disk (not necessarily the onedrive root directory).
 ### index.html
 show content of index.html as html. Display index.html as a static web page.
 ### head.md readme.md
 it will showed at top or bottom as markdown. It will show at top or bottom as markdown.
 ### head.omf foot.omf
 it will showed at top or bottom as html (javascript works!). It will show at top or bottom as html (javascript works!).

 QQ Group: 212088653 (please read the Chinese and English bilingual above and add the group, thank you!)
 Telegram Group: https://t.me/joinchat/I_RVc0bqxuxlT-d0cO7ozw
