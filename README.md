# Ex.No:3 Develop a simple application to play and control the audio file in android studio.
            mediaPlayer = null;
        }
    }
}
~~~
## activity_main.xml:
~~~
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:background="?android:attr/windowBackground"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Audio Player"
        android:textSize="24sp"
        android:textStyle="bold"
        android:layout_marginBottom="32dp" />

    <Button
        android:id="@+id/btnPlay"
        android:layout_width="200dp"
        android:layout_height="wrap_content"
        android:text="Play"
        android:layout_marginBottom="16dp" />

    <Button
        android:id="@+id/btnPause"
        android:layout_width="200dp"
        android:layout_height="wrap_content"
        android:text="Pause"
        android:layout_marginBottom="16dp" />

    <Button
        android:id="@+id/btnStop"
        android:layout_width="200dp"
        android:layout_height="wrap_content"
        android:text="Stop" />

</LinearLayout>
~~~

## OUTPUT




## RESULT
   Thus a simple application, to play and control the audio file and to perfrom the start,pause and stop opeartion in Android Studio is developed and executed successfully.
