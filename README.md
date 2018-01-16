# Web-Project
User Documentation

Overview

The name of our website is Mini Piazza. It aims to provide students a public community to ask questions about courses or everything interesting in their life. Compared with Piazza, the UI design of our website is more colorful and neat. Now, let’s start using it.

Home Page


After we enter the website, home page will appear first. There is a navigation bar at the top of this page. When we haven’t logged in it will shows “sign up” and “login” at the right top corner. Once we’ve logged in these two button will be changed into a drawer named “User”.

Let’s first start without login. Here we can see all previous posts without having to login like Figure.1. Every item in homepage will show avatar of the poster, title, content, pictures, name of the poster, post time and a little star for collection. All items are sorted in decreasing order of post time. If we need to see details of an item, just click its title then we will be directed to a detailed page where we can also comment on it. Click the thumbnail in this detailed page, the picture will be enlarged to full screen like Figure.2 and Figure.3. (Note: If we try to make a comment or new post, it will direct us to login page to ask us login first.)
 

Fugure.1
 

 

Figure.2

 
Fugure.3
Now, let’s login to see what changed. After we login, our avatar will appear at the top left corner of the home page, and below it there is a little blue arrow which is a drawer for tags and confirm button of collection function like Figure.4. By clicking the title below “tag”, we can see all items under this tag. And if we want to collect one or more items, we need to first click the empty star at the left bottom corner of the item we want to collect and then click “Collect” button in this drawer. Then every time we are in home page, we can see stars of the items that we collected will be shining like Figure.5. And we can also see all the collections by clicking “Collection” button under the “User” drawer after we login like Figure.6.
 

 
Figure.4

 
Figure.5

 
 
Figure.6

New Post

If we want to post a new item, we need to first login or once we click “New Post” button we will be directed to Login page automatically. The New Post page is like Figure.7. It allows us to upload pictures and show the thumbnail of picture. Note we only allow user to upload pictures which is less than 1000KB, or it will return us a warning message like Figure.8. Of course I can also change this limitation in my code to other size. If the size of picture is legal, it will show thumbnails of them like Figure.9. Click “Post Now”, we’ll see this new post in home page.
 
Figure.7

 
Figure.8
 

 
Figure.9

Search

“Search” button in navigation bar allows us to search all items that contain certain key word both in their title and content. Just type our key word and the items shown in current page will be the result like Figure.10.
 
Figure.10

Sign Up and Login

By clicking sign up and Login button on navigation bar, we will be directed to these two pages. In order to attract more people to use our website, we make a carousel effect for background like Figure.11 and Figure.12. Since Piazza is a community mainly for academic questions, which means time is precious so we add a semi-transparent clock to remind user the flowing of time. The process for login and sign up is just as normal as other websites. And user’s information including account’s creating time will be stored in
 
dynamodb. Also the password will be add salted value and hashed.

 
Figure.11

 
Figure.12

User

After login, there will be a “user” button on the right up corner of the page. When you click it, there will be a dropdown-menu showing up which contain four sublabels: “information”,”password”,”collection”,”logout”, as shown in Figure.13
 

 

Figure.13

User Information

When you click information button, the website will jump to userinformation page as shown in Figure.14

 
Figure.14
Where you can click the profile and then you can select the profile image you want to update. No matter what size of the image you up load, the imagemagick will resize the image to 250*250px.and you can only image with suffix 'png', 'jpg', 'jpeg', 'gif'.

Below the userinformation page are all the answers you have been posted(sorted in createtime) ,as shown in Figure.15,and you can either click a title to see the details of the question or click the ‘delete’ button to delete the question you have been post.
 

 

Figure.15

Change password

When you click the “change password” bottom, you can change the password of the user. the page is as shown in Figure.16. Make sure that you input the same password twice, otherwise it will return a error message as shown in Figure.17. After you have change the password successfully, the page will redirct to index page.

 
Figure.16
 

 

Figure.17

Logout

When you click the “logout” button, you will logout and the yours session will be popped out, and the page will redirect to login page, just as shown in the Figure.18
.

 
Figure.18



Loading

Between some pages we also add a loading page to let user know that the page is loading please wait like Figure.19
 

 
Figure.19

