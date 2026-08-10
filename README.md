# A comprehensive guide to 360 photos on Google maps
<a name="top"></a>
A how to guide on **creating**, **uploading** and **updating** 360 photos on Google maps with **no API key needed!**

This is meant for **everyone** - **beginners** with little technical knowledge up to **professionals**.


| Symbol        | Meaning           |
| ------------- |:-------------:|
| 🟢| Easy. Little technical knowledge is required. |
| 🟡| Medium. Some technical knowledge is required.      |
| 🔴| Hard. A lot of technical knowledge is required.      |
| ⚪| Unrated. Usually just information.|

**Don't let these symbols scare or discourage you though!**

### Table of contents

  * [Creating 360 photo spheres (phone) 🟢/🟡](#creating-360-photo-spheres-phone-)
  * [Uploading 360 photos to Google maps 🟢](#uploading-360-photos-to-google-maps-)
  * [Photos upload info/FAQ ⚪](#photos-upload-infofaq-)
  * [Finding a placeId 🟢](#finding-a-placeid-)
  * [Creating a traverse-able photo tour 🟡](#creating-a-photo-tour--traverse-able-photos-)
  * [Using APIs - general guide 🟡](#using-apis---general-guide-)

## Creating 360 photo spheres (phone) 🟢/🟡
[⬆ Back to top](#top)

If you already have a 360 photo or are using a specialized camera to create them, feel free to skip this section.

Getting a working app is **really hard**. There is **no universal working app** that's free to take 360 photos. There are a lot of paid apps to create 360 photos which work and some free ones which work for some users but don't for others.

I personally use [Go Street View Photo Sphere 🟢](https://play.google.com/store/apps/details?id=com.gostreetview.camera) (android) despite it not working for a lot of people.

Some people also use the **deprecated** [Street view app from Google 🟡](https://www.apkmirror.com/apk/google-inc/street-view/). You can download the latest version to see if it works for you (it didn't for me), or one of the older versions (I remember one of the old ones working). You can still test out different versions - maybe one of them will work.

I'm not aware of any other working apps (especially for iPhone) which are free, so **any suggestions are appreciated!**

## Uploading 360 photos to Google maps 🟢
[⬆ Back to top](#top)

This is the easiest and simplest way to upload your photos.

There exists a great upload tool - [PhotoSphereStudio](https://maps.moomoo.me/), which is an **open source** project on Github.

Here I will try to explain how to use it.

When you first open the site, you will have to **log in** using your **Google account**. Log in and grant it the necessary permissions.

After that, you are able to add an image. When you do, the website automatically **loads the information** from it like the coordinates (if there are any). You can always set custom coordinates - either because the website didn't detect any or because you want a more precise location for the photo.

For individual photos (not planning on making a photo tour/traverse-able photos), you generally **don't** have to set the **Heading/pose**. However, if you are planning on making a **walk-able photo tour** (with the arrows), I **HEAVILY** recommend setting it.

At the bottom, there is an "advanced options" option - click it. At the bottom now there is an optional field to set a placeId, which I **heavily recommend** you do - since this will associate the photo with a place instead of showing it as being an unknown place. You can check the [finding a placeId](#finding-a-placeid-) section. Also if you later need to find the photo's information, you can filter by the placeId

The website also gives you the "Publish url as a marker to this website's map and backup image?" - which is up to you. Later deleting the image means it will also delete from the website.

Then you are **ready to upload the photo** - click on the "Upload" button and wait a bit for the website to process it. If you did everything right, will get a link for Google maps! You can also click the debug information option, where you will find the **ID of the photo**, which may be useful for other things in this guide.

Please check the [**Photos upload info/FAQ**](#photos-upload-infofaq-) section now!

## Photos upload info/FAQ ⚪
[⬆ Back to top](#top)

When you upload a photo, you have to **wait a few minutes** for it to start displaying a photo and for it to appear in your contributions tab on Google maps. Just keep refreshing the page using **CTRL + F5** (make sure to refresh this way due to the cache) until you see your photo! On phones, try to either wait longer or clear your browser's cache if you don't see your photo yet. If you have set any **placeId's**, you should be able to see the photo when you view the place on maps (though if the place has a lot of photos yours might be buried deep between them) - also in a few minutes.

When your photo gets uploaded, it will **NOT APPEAR** as a **blue circle (YET)**. It may take up to **three days** for your photo to appear as a blue circle on maps, if Google's algorithm deems it fit. There is no guarantee that it will appear as a blue circle, but from my testing, all of my photos did. You just have to be **patient**.

## Finding a placeId 🟢
[⬆ Back to top](#top)

I recommend using [this website](https://geo-devrel-javascript-samples.web.app/samples/places-placeid-finder/app/dist/) to find the placeId. Just open it, search for your place in the top left, select it and then copy the placeId from the map. Warning - you **HAVE to SEARCH** for it, just finding it and clicking on it won't give you the placeId.

## Creating a photo tour / traverse-able photos 🟡
[⬆ Back to top](#top)

If you want to create a photo tour (like the street view images with arrows), here is how to do it.
First, [upload your photos](#uploading-360-photos-to-google-maps-) and **remember their IDs** - up to you on how you do it. Make sure to set the **Heading/pose**.

## Using APIs - general guide 🟡
[⬆ Back to top](#top)

This is a simple guide on how to generally use the APIs, which are in some of the sections in this guide. In the examples below, the API for updating photos will be used - but this is **general info for all of the APIs** here.

For using the APIs, I recommend doing this on **a notebook**. If you are using a phone, you have to use the **desktop version** of the website.

Now onto how to actually use them. Your page will open with **a lot of info** - fortunately you can **ignore most of it**. Focus on the **panel on the right** and **click the API button**.

<img width="1920" height="1060" alt="Screenshot From 2026-08-10 20-42-27" src="https://github.com/user-attachments/assets/df38c33f-9ff5-4a5d-bfb2-504a0d90c94e" />

A **window will** open, which will look something like this (you may need to scroll up/down). The window has **three main parts** - **"Request parameters"**, where you will usually set things like the photo's ID. Then the **"Request body"** - you will usually find a template body in the API guide with some TEMPLATE_VARIABLES (indicated by the caps lock and underscores instead of spaces). You should **edit the template body** (eg. replace latitude/longitude text with actual values) and then you can **paste the whole body into the section** with two curly braces - just delete them and instead place the edited body template there. Lastly, the blue **"Execute" button** - when you open the page for the first time (or after a long time), it will ask you to **log in** and give it permission to edit things on your account. This is safe since this is google's official API - you need to **give the permissions** for everything to work. **YOU SHOULD ONLY ENTER THE PARAMETERS WHICH ARE IN THE GUIDE, OTHERWISE YOU MAY BREAK YOUR PHOTOS** - unless you read through the documentation on the pages and you understand how it works.

<img width="486" height="1003" alt="image" src="https://github.com/user-attachments/assets/df961411-42cb-4205-be1c-a5c8278c196e" />

Lastly, when you have all of the values and the body filled in, **click the execute button**. It might take a moment, but a **response will appear underneath**. The response will include a number - the **number 200 meaning it was correct**. Also - generally, the response includes the photo's ID if it was correct.
