# Build your users profile

TongDao help you to understand your users by gathering your users profile and behaviors. TongDao SDK will track basic information about users such as their device, location, sessions, etc… This is sufficient if you want to use the generic segmentation capability of TongDao, however to use the full segmentation capability and message customization of TongDao you will need to integrate user data points specific to your application. For example :

- <b>Identify</b> a user name to include it later in a personalized message
- <b>Track</b> whenever a user finish a level to detect hardcore gamers

TongDao offers 2 ways to collect user information, track to record events that happens within the application and identify to record attributes of a particular user. The SDK allow you to record both custom and predefined event and attribute. If you wish to record custom ones, please remember to create them in the portal beforehand.
<br>

### Identifying Custom Attributes

You can identify a single attribute:
```java
tongDao.identify("coin_balance", 4500);
```
<br>

Or you can identify multiple attributes:
```java
HashMap<String,Object> values = new HashMap<String,Object>();
values.put("coin_balance", 4500);
values.put("favourite_color", "purple");
tongDao.identify(values);
```
<b>Note: The attribute name cannot start with the "!" character</b>
<br>

### Identifying Custom Events

You can identify an event without properties:
```java
tongDao.track("event_name");
```
Or identify an event with properties:
```java
HashMap<String,Object> values = new HashMap<String,Object>();
values.put("id", 2);
values.put("character","dawrf");
tongDao.track("finish_level", values);
```

<b>Note: The event and parameter name only support A-Z, a-z, 0-9 and ‘-’, ‘_’</b>

### Predefined Attribute Methods

Method | Description
-------|------------
identifyFullName(String fullName) | Set user full name
identifyFullName(String firstName, String lastName | Set user's first and last name
identifyUserName(String userName) | Set the user's username
identifyEmail(String email)	      | Set user email, this attribute is used when doing an email campaign
identifyPhone(String phoneNumber) | Set user phone number, this attribute is used when doing a sms campaign
identifyGender(TdGender gender)   | Set user gender
identifyAge(int age)              | Set user age
identifyAvatar(String url)        | Set user avatar
identifyBirthday(Date date)       | Set user birthday
identifySource(TdSource source)   | Set App Store and referrers of the application
identifyRating(int rating)        | Set the rating of the app by the user
identifyAddress(String address)   | Set user postal address
<br>

### Predefined Event Methods

Method | Description
-------|------------
trackRegistration() | Track user registration date, use the current time
trackRegistration(Date date) | Track user registration date, the date can be passed as a parameter

[See the documentation here to track e-commerce activity][ecommerce]


[ecommerce]: ecommerce.md