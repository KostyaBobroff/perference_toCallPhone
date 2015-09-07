# perference_toCallPhone
<?xml version="1.0" encoding="utf-8"?>
<PreferenceScreen xmlns:android="http://schemas.android.com/apk/res/android">
    <PreferenceCategory
        android:title="First Category">
        <EditTextPreference
            android:name="EditText Preference2"
            android:summary="This is your id"
            android:defaultValue=""
            android:title="Edit This id"
            android:key="editTextPref2" />
    </PreferenceCategory>
    <PreferenceCategory
        android:title="Second Category">
        <EditTextPreference
            android:name="EditText Preference"
            android:summary="This allows you to enter a phone number"
            android:defaultValue="000"
            android:inputType="phone"
            android:title="Edit This Number"
            android:key="editTextPref" />

        <Preference
            android:title="Custom Preference"
            android:summary="This works almost like a button"
            android:key="customPref" />
    </PreferenceCategory>
</PreferenceScreen>
