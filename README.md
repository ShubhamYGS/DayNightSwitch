# DayNightSwitch
This is demo project of Day-NIght Switch. (Android Studio)
Special thanks to Mahfa for this awesome project.


![daynightswitch](https://user-images.githubusercontent.com/33577947/51070633-76fac080-166a-11e9-82fb-6998a3de9c43.gif)


## How to get?

### Step1: Add this line in build.gradle(project) (maven line)
```
allprojects {
    repositories {
        google()
        jcenter()
        maven { url 'https://jitpack.io' }
    }
}
```

### Step2: Add this line in build.gradle(app)
```
implementation 'com.github.Mahfa:DayNightSwitch:1.2'
```

### Step3: Activity_Main.xml
```
<View
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:alpha="0"
        android:background="@android:color/background_dark"
        android:id="@+id/background_view"
        />

    <com.mahfa.dnswitch.DayNightSwitch
        android:layout_width="76dp"
        android:layout_height="40dp"
        android:layout_centerInParent="true"
        android:id="@+id/day_night_switch"
        />
```

### Step4: MainActivity.java
```
    DayNightSwitch dayNightSwitch;
    View backgroundView;
    
     dayNightSwitch = (DayNightSwitch)findViewById(R.id.day_night_switch);
        backgroundView = (View)findViewById(R.id.background_view);

        dayNightSwitch.setDuration(450);
        dayNightSwitch.setListener(new DayNightSwitchListener() {
            @Override
            public void onSwitch(boolean isNight) {
                if(isNight)
                {
                    Toast.makeText(MainActivity.this,"Night mode Selected",Toast.LENGTH_SHORT).show();
                    backgroundView.setAlpha(1f);
                }
                else
                {
                    Toast.makeText(MainActivity.this,"Day mode Selected",Toast.LENGTH_SHORT).show();
                    backgroundView.setAlpha(0f);
                }
            }
        });
    }
```

###Step5: Done! :)
    
    
