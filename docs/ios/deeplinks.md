# Help on Deep Links

To enable users to enter your app from websites or ads, you must add intent filters for the relevant activities in your app manifest. These intent filters allow <i>deep linking</i> to the content in any of your activities. For example, the user might click on a deep link to view a page within a shopping app that describes a product offering that the user is interested by.
<br>
<br>

You need to add an intent-filter directive to any activity you want to open via a deeplink. The property <b>android:scheme</b> should represent your application name and the property <b>android:host</b> should represent the activity to open.

```xml
<activity android:name="AddCartActivity">
	<intent-filter>
		<action android:name="android.intent.action.VIEW" />
		<category android:name="android.intent.category.DEFAULT" />
		<category android:name="android.intent.category.BROWSABLE" />
		<data android:scheme="tongrd" android:host="add_cart"/>
	</intent-filter>
</activity>
```
<br>

Note: In this example, our activity AddCartActivity can be directly opened from a webpage, using the url : tongrd://add_cart.

Once the activity starts, you can use this code to get information from the deeplink:

```java
@Override
public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.main);

    Intent intent = getIntent();
    String action = intent.getAction();
    Uri data = intent.getData();
}
```
<br>

For more information, please refer to the [official android documentation][deeplink] on deep links.

[deeplink]: https://developer.android.com/training/app-indexing/deep-linking.html