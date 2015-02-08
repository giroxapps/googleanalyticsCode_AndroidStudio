# googleanalyticsCode_AndroidStudio
How to connect youir app with google analitycs

1.	Copiare libreria libGoogleAnalitycsServices.jar e schiacciare il tasto   sync nella barra degli strumenti android studio.
2.	Inserie il codice in rosso nellaclasse java:
import com.google.analytics.tracking.android.EasyTracker;
import com.google.analytics.tracking.android.MapBuilder;

public class MainActivity extends ActionBarActivity {
    private EasyTracker easyTracker = null;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        easyTracker = EasyTracker.getInstance(MainActivity.this);

button.setOnclickListener(){
   easyTracker.send(MapBuilder.createEvent("string,
                                "string", "string,value).build()); 
}
    }
p.s:tramine il metodo send()   easyTracker invierà i dati a google analitycs. Questo medoto di solito viene inserito all’interno dell’ascoltatore di eventi del widget desiderato.

3.Copiare nel file analitycs(opportumanente creato  ) le seguenti linee di  codice:

<!-- Replace placeholder ID with your tracking ID -->
    <string name="ga_trackingId">UA-xxxxxx-x</string>
   //sostituire questo codice con quello fornito da googleAnalitycs al   momento della registrazione.
    <!-- Enable automatic activity tracking -->
    <bool name="ga_autoActivityTracking">true</bool>

    <!-- Enable automatic exception tracking -->
    <bool name="ga_reportUncaughtExceptions">true</bool>


