# perference_toCallPhone
public class MainActivity extends Activity {
    boolean CheckboxPreference;
    String ListPreference;
    String editTextPreference2;
    String editTextPreference;
   String ringtonePreference;
       String secondEditTextPreference;
       String customPref;

    @Override
    protected void onStart() {
        super.onStart();
        getPrefs();
    }

    private void getPrefs() {
        // Get the xml/preferences.xml preferences
        SharedPreferences prefs = PreferenceManager
                .getDefaultSharedPreferences(getBaseContext());
      //  CheckboxPreference = prefs.getBoolean("checkboxPref", true);
       // ListPreference = prefs.getString("listPref", "nr1");
        editTextPreference2=prefs.getString("editTextPref2","");
        editTextPreference = prefs.getString("editTextPref",
                "Nothing has been entered");
     /*   ringtonePreference = prefs.getString("ringtonePref",
                "DEFAULT_RINGTONE_URI");
        secondEditTextPreference = prefs.getString("SecondEditTextPref",
                "Nothing has been entered");*/
        // Get the custom preference
        SharedPreferences mySharedPreferences = getSharedPreferences(
                "myCustomSharedPrefs", Activity.MODE_PRIVATE);
        customPref = mySharedPreferences.getString("myCustomPref", "");
    }
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main);
        Button prefBtn = (Button) findViewById(R.id.prefButton);
        Button call = (Button) findViewById(R.id.button);
//String number=editTextPreference;
        call.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                Intent phoneIntent = new Intent(Intent.ACTION_CALL);
                phoneIntent.setData(Uri.parse("tel:"+editTextPreference.toString()));
                startActivity(phoneIntent);
            }
        });
        prefBtn.setOnClickListener(new View.OnClickListener() {

            public void onClick(View v) {
                Intent settingsActivity = new Intent(getBaseContext(),
                        Preferences.class);
                startActivity(settingsActivity);
            }
        });
    }
}
