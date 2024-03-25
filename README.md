create CONSTS.js folder in the src folder and fill your credentials

export const COMETCHAT_CONSTANTS = {
  APP_ID: '**************',
  REGION: '**************',
  AUTH_KEY: '**************',
}

# Chatty documentation

Created: April 21, 2022 2:01 PM
Language: Vue.js
Demo: https://drive.google.com/file/d/1ecieBZCHs-yWxqXpUnHHayCKVANc5wIY/view?usp=sharing
Property: Sara Peksin

**Tech stack:**

- Vue.js
- CometChat

**Dependencies:**

- cometchat-pro/chat
- core-js
- dateformat
- emoji-mart-vue-fast
- twemoji
- vue-router

**Views**

- Welcome page
- Chat page

**Components**

- Bottom navigation
- Chatbox sidebar
- More (profile, preferences, other)
- Groups
- Message Box

**Welcome page**

This page includes an option to log in in two ways. Hypothetically saying that the user doesn’t have an account, he can log in with pre-made ones by just clicking on them. If the user wants to log in, he needs to have a UID which is provided to him by the administrator. 

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled.png)

For this example, we will log in with the credentials that are given to us.  The UID we will enter is *admin.* After that, in the dashboard of CometChat, we will get a new activity displayed.

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%201.png)

Because this application is imagined to be more than just a chatting application, we thought to display different cards for different sections of the app. Right now the only one we have is the one for that, but later on, it will be updated. Then just click on *Launch the app.*

**Chat page**

After successful login and launching, you will be presented with an initial screen for chatting. This screen consists of two parts: a list of users you have talked to and a chat window. Chat window offers a great variety of functionality like sending files, emojis, stickers, message status, video calls, phone calls, and lists of sent photos, videos, and documents. List of users on the left side there is a display of all users that you have messaged before, as well as saved previous conversations. 

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%202.png)

**Bottom navigation**

This component consists of four main parts: chats, a list of users, groups, and personal information. By changing the active tab, the content on the sidebar is changed.

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%203.png)

**User list**

This component shows all the users that are located in the database. They are sorted alphabetically and on each click on the user, a new chatbox opens. This component also allows you to search through the list by typing a few letters that you can remember. 

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%204.png)

**Groups**

This is a component where you can create a new group or see a list of the groups you are already in. Seeing a list is pretty self-explanatory so, now we will show you how to create a new group and what you can do with it.

Step 1. On the top left corner click on the icon 

Step 2. Now you will be shown a dialog with a few fields

Step 3. Enter the desired group name 

Step 4. Choose a group type. You can choose from three options: Public, private, password-protected

Step 5. Click on the Create button and your creative group will be a part of the group list

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%205.png)

**Profile**

This component allows you to turn on or off notifications, get more information about the web application, report a problem, and see the status of a user.

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%206.png)

**Chatbox sidebar**

This is a place where you can see all of the videos, photos, or documents that you or your friend have sent. If you for some reason want to block the user, you can simply do that and confirm the dialog, and your selected user will be blocked.

If you have previously selected a group chat, on this same bar, you will have a little bit more options such as member details, removing members, or deleting a group.

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%207.png)

**Message Box**

The message box consists of a few parts: Textarea, uploading media files and stickers, and emojis section. 

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%208.png)

When it comes to uploading the media section you can attach a video, audio, or image, upload a file, or create a poll. Creating a poll allows members of a group to vote on different things. By clicking the last icon that has a plus sign inside the message icon, you will be presented with a dialog. 

![Untitled](Chatty%20documentation%20c59a73ba53fc41cfbb4d818435128df4/Untitled%209.png)

Simply fill out a form and the members can vote on all the options that are given to them.
