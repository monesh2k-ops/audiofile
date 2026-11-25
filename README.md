# Ex.No:3 Develop a simple application to play and control the audio file in android studio.


## AIM:

To develop a simple application, to play and control the audio file and to perfrom the start,pause and stop opeartion in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Artic Fox)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as audiofile and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml and create start,pause and stop button.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to play and control the audio file”.
Developed by:MONESH S
Registeration Number :212225230183
*/
```
## MainActivity.java:
~~~
package com.example.exp_4;

import android.media.MediaPlayer;
import android.os.Bundle;

import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {

    private MediaPlayer mediaPlayer;
    private Button btnPlay, btnPause, btnStop;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        WindowCompat.enableEdgeToEdge(getWindow());
        setContentView(R.layout.activity_main);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });

        btnPlay = findViewById(R.id.btnPlay);
        btnPause = findViewById(R.id.btnPause);
        btnStop = findViewById(R.id.btnStop);

        // Setting up the MediaPlayer with a default system sound to work immediately.
        // To use your own file, create a "raw" resource folder (res/raw), add "song.mp3",
        // and replace the following line with: mediaPlayer = MediaPlayer.create(this, R.raw.song);
        mediaPlayer = MediaPlayer.create(this, R.raw.om_movie_bgm);

        btnPlay.setOnClickListener(v -> {
            if (mediaPlayer == null) {
                mediaPlayer = MediaPlayer.create(MainActivity.this, R.raw.om_movie_bgm);
            }
            if (!mediaPlayer.isPlaying()) {
                mediaPlayer.start();
                Toast.makeText(MainActivity.this, "Playing Audio", Toast.LENGTH_SHORT).show();
            }
        });

        btnPause.setOnClickListener(v -> {
            if (mediaPlayer != null && mediaPlayer.isPlaying()) {
                mediaPlayer.pause();
                Toast.makeText(MainActivity.this, "Audio Paused", Toast.LENGTH_SHORT).show();
            }
        });

        btnStop.setOnClickListener(v -> {
            if (mediaPlayer != null) {
                mediaPlayer.stop();
                mediaPlayer.release();
                mediaPlayer = null;
                Toast.makeText(MainActivity.this, "Audio Stopped", Toast.LENGTH_SHORT).show();
            }
        });
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        if (mediaPlayer != null) {
            mediaPlayer.release();
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
<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/22c95a3c-0739-4b09-bb7e-c5ba621f03ef" />

<img width="408" height="745" alt="image" src="https://github.com/user-attachments/assets/ffb702f0-253f-4274-8f34-6dc459a8cd34" />


## RESULT
   Thus a simple application, to play and control the audio file and to perfrom the start,pause and stop opeartion in Android Studio is developed and executed successfully.
