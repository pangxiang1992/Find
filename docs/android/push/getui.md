# Quick Start

The Tongdao API for Android can be configured in two ways. If you use Gradle, see the "Quick Start - Android Studio" section. Otherwise, if you use Eclipse, see the "Quick Start - Eclipse" section.
<br>
<br>

### 1. Android Studio Installation

In your <b>app module's</b> `build.gradle`, add the following dependency:

    compile 'com.tongdao.sdk:sdk:3.2.0-beta@aar'
    

You may now continue to step 3.
<br><br>

### 2. Eclipse Installation

To start, download the Tongdao eclipse archive from here:
<br>
<h4><center><a href="#"><b>TongDao Eclipse SDK</b></a></center></h4>
<br>
Unpack it and you will see two projects: demo and sdk. In Eclipse, click "File" -> "Import". Choose "Android" -> "Existing Android Code Into Workspace"
![Screenshot](img/android-eclipse-1.jpeg)

![Screenshot](img/android-eclipse-2.jpeg)

Once the SDK project is imported, right-click it and click "Properties". Then click on the "Android" section on the left. Make sure the <b>build target</b> of the SDK is set to <b>Android 7.1.1 (api 25)</b>.
Also, make sure that <b>"Is Library"</b> is checked.
![Screenshot](img/android-eclipse-3.jpeg)

Now, right-click on your own project, click "Properties". Go into the "Android" section and make sure that "SDK" is added as a library.
![Screenshot](img/android-eclipse-4.jpeg)

### 3. Code Integration
<br>
Next, you will need an `Application` object. If you already have an application object in your code, skip this part.

<br>
In your `AndroidManifest.xml` add the following:

	<uses-permission android:name="android.permission.INTERNET" />
	<uses-permission android:name="android.permission.READ_PHONE_STATE" />
	<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
	
    <application
        ...
        android:name="TongDaoApplication"
        ...>
    
You can replace `TongDaoApplication` with whatever other name you'd like.
<br>
<br>

In your `TongDaoApplication`, add the following code:
    
    public class TongDaoApplication{
    
    ...
    
    	private TongDao tongDao;

    	@Override
    	public void onCreate() {
        	super.onCreate();
        	if (tongDao == null){
            	tongDao = TongDao.getInstance(this,DataTool.APP_KEY);
        	}
    	}

    	synchronized public TongDao getTongDao() {
        	if (tongDao == null){
            	tongDao = TongDao.getInstance(this,DataTool.APP_KEY);
        	}
        	return tongDao;
    	}
    
    ...
    
    }
    
now you'll be able to access the TongDao SDK through this object in your activities.

If you <b>have the user ID</b> of your app's user, you can call our SDK this way instead:

	tongDao = TongDao.getInstance(this,DataTool.APP_KEY,userId);

<br>
### 4. Logging in

When the user logs in, you can call this function:
	
	tongDao.login(appContext, userId);
<br>
### 5. Logging out
	
Likewise, when the user logs out, you can call this function:

	tongDao.logout(appContext);
	
<br>
<br>
### 6. Next Steps

That’s it, TongDao is now integrated in your application ! Take a look at the next steps to unleash TongDao full potential.
<br>
<br>
<!--#### [Send your users a push, in-app, email or sms message][push]<br>-->
#### [Build your user profiles][profile]<br>
#### [Track E-Commerce activity][ecommerce]<br>
<!-- [Activate Retargeting][ -->
#### [Help on Deep Links][deeplinks]<br>

<!--[push]: push/intro.md-->
[profile]: user_profile.md
[ecommerce]: ecommerce.md
[deeplinks]: deeplinks.md
