Instruções para criar o WebView no Android Studio.


* Crie um projeto em branco.
* Crie a pasta **assets** dentro da pasta *app/src/main/*
* Coloque seu site dentro da pasta **assets**
* Edite os seguintes arquivos:

**activity_main.xml**

~~~xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
   xmlns:tools="http://schemas.android.com/tools"
   android:layout_width="match_parent"
   android:layout_height="match_parent"
   android:orientation="vertical"
   tools:context=".MainActivity">

   <WebView
      android:id="@+id/webView"
      android:layout_width="match_parent"
      android:layout_height="match_parent"/>
</LinearLayout>
~~~

**MainActivity.java**

~~~java
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.webkit.WebView;

public class MainActivity extends AppCompatActivity {
   @Override
   protected void onCreate(Bundle savedInstanceState) {
      super.onCreate(savedInstanceState);
      setContentView(R.layout.activity_main);
      WebView webView = findViewById(R.id.webView);
	WebSettings webSettings = webView.getSettings();
        webSettings.setJavaScriptEnabled(true);
        webSettings.setDomStorageEnabled(true);
      webView.loadUrl("file:///android_asset/mytext.html");
   }
}
~~~

* Depois faça as alterações necessárias de cores e temas nos arquivos **themes.xml** dentro da pasta *res/values/themes*
