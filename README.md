# Web-Project
## How to deploy the web

All lecture and tutorial examples require the following in order to work:
    - Python 2.7
    - A python virtual environment
    - Flask
    - zappa
    - AWS CLI 

Perform these steps to run the examples:

1) Install python 2.7 by following the instructions for your respective platform available at https://www.python.org/

2) Download and unpack the file:

   a) Download the example sources,
   b) Open a shell and navigate to the location of the tar.gz file
   c) Uncompress and untar (e.g., tar -xzf Flask_web_demo1.tar.gz)
   d) Go into the example directory (e.g., cd Flask_web_demo1)

3) Create a new python virtual environment as follows:

   python -m venv venv


4) Activate the virtual environment

   source venv/bin/activate

5) Install Flask

   pip install flask

6) Install AWS Command Line Interface (CLI)

   Follow instruction in https://aws.amazon.com/cli/

7) Install zappa

   pip install zappa

7) Before you can begin using zappa, you should set up authentication
credentials. Credentials for your AWS account can be found in the IAM
Console at https://console.aws.amazon.com/iam/home?#. You can create
or use an existing user. Go to manage access keys and generate a new
set of keys.  You will need both the aws_access_key_id and
aws_secret_access_key.

8) Configure your credentials

   aws configure

9) Edit the file zappa_settings.json.  Set the value of the key "s3_bucket" to
   the name of one of your existing S3 buckets.

10) Deploy the example on AWS Lambda

   zappa deploy dev
11) Or you can run locally
    
   python run.py






# User Documentation

## Overview

The name of our website is Mini Piazza. It aims to provide students a public community to ask questions about courses or everything interesting in their life. Compared with Piazza, the UI design of our website is more colorful and neat. Now, let’s start using it.

## Home Page


After we enter the website, home page will appear first. There is a navigation bar at the top of this page. When we haven’t logged in it will shows “sign up” and “login” at the right top corner. Once we’ve logged in these two button will be changed into a drawer named “User”.

Let’s first start without login. Here we can see all previous posts without having to login like Figure.1. Every item in homepage will show avatar of the poster, title, content, pictures, name of the poster, post time and a little star for collection. All items are sorted in decreasing order of post time. If we need to see details of an item, just click its title then we will be directed to a detailed page where we can also comment on it. Click the thumbnail in this detailed page, the picture will be enlarged to full screen like Figure.2 and Figure.3. (Note: If we try to make a comment or new post, it will direct us to login page to ask us login first.)
![Alt text](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure1.jpg)
Figure.1
 

![Alt text](https://github.com/Hanmu-Zuo/Web-Project/raw/master/Figure2.jpg)

Figure.2

![Alt text](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure3.jpg)
Fugure.3
Now, let’s login to see what changed. After we login, our avatar will appear at the top left corner of the home page, and below it there is a little blue arrow which is a drawer for tags and confirm button of collection function like Figure.4. By clicking the title below “tag”, we can see all items under this tag. And if we want to collect one or more items, we need to first click the empty star at the left bottom corner of the item we want to collect and then click “Collect” button in this drawer. Then every time we are in home page, we can see stars of the items that we collected will be shining like Figure.5. And we can also see all the collections by clicking “Collection” button under the “User” drawer after we login like Figure.6.
 

![Alt text](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure4.jpg)
Figure.4

![Alt text](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure5.jpg)
Figure.5

 
![Alt text](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure6.jpg) 
Figure.6

## New Post

If we want to post a new item, we need to first login or once we click “New Post” button we will be directed to Login page automatically. The New Post page is like Figure.7. It allows us to upload pictures and show the thumbnail of picture. Note we only allow user to upload pictures which is less than 1000KB, or it will return us a warning message like Figure.8. Of course I can also change this limitation in my code to other size. If the size of picture is legal, it will show thumbnails of them like Figure.9. Click “Post Now”, we’ll see this new post in home page.
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure7.jpg) 
Figure.7

![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure8.jpg) 
Figure.8
 
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure9.jpg)
 
Figure.9

## Search

“Search” button in navigation bar allows us to search all items that contain certain key word both in their title and content. Just type our key word and the items shown in current page will be the result like Figure.10.
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure10.jpg) 
Figure.10

## Sign Up and Login

By clicking sign up and Login button on navigation bar, we will be directed to these two pages. In order to attract more people to use our website, we make a carousel effect for background like Figure.11 and Figure.12. Since Piazza is a community mainly for academic questions, which means time is precious so we add a semi-transparent clock to remind user the flowing of time. The process for login and sign up is just as normal as other websites. And user’s information including account’s creating time will be stored in
 
dynamodb. Also the password will be add salted value and hashed.
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure11.jpg)
 
Figure.11
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure12.jpg)
 
Figure.12

## User

After login, there will be a “user” button on the right up corner of the page. When you click it, there will be a dropdown-menu showing up which contain four sublabels: “information”,”password”,”collection”,”logout”, as shown in Figure.13
 

 
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure13.jpg)
Figure.13

## User Information

When you click information button, the website will jump to userinformation page as shown in Figure.14
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure14.jpg)
 
Figure.14
Where you can click the profile and then you can select the profile image you want to update. No matter what size of the image you up load, the imagemagick will resize the image to 250*250px.and you can only image with suffix 'png', 'jpg', 'jpeg', 'gif'.

Below the userinformation page are all the answers you have been posted(sorted in createtime) ,as shown in Figure.15,and you can either click a title to see the details of the question or click the ‘delete’ button to delete the question you have been post.
 

 
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure15.jpg)
Figure.15

## Change password

When you click the “change password” bottom, you can change the password of the user. the page is as shown in Figure.16. Make sure that you input the same password twice, otherwise it will return a error message as shown in Figure.17. After you have change the password successfully, the page will redirct to index page.

![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure16.jpg) 
Figure.16
 

 
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure17.jpg)
Figure.17

## Logout

When you click the “logout” button, you will logout and the yours session will be popped out, and the page will redirect to login page, just as shown in the Figure.18
.
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure18.jpg)
 
Figure.18



## Loading

Between some pages we also add a loading page to let user know that the page is loading please wait like Figure.19
 
![image](https://github.com/Hanmu-Zuo/Web-Project/blob/master/Figure19.jpg)
 
Figure.19

