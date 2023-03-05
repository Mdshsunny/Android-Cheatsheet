> build.gradle
```gradle
implementation 'com.google.android.material:material:1.6.1'
```

> MainActiviy.java
```java
        // drawer layout instance to toggle the menu icon to open  
        // drawer and back button to close drawer 
        drawerLayout = findViewById(R.id.my_drawer_layout); 
        actionBarDrawerToggle = new ActionBarDrawerToggle(this, drawerLayout, R.string.nav_open, R.string.nav_close); 

        // pass the Open and Close toggle for the drawer layout listener 
        // to toggle the button 
        drawerLayout.addDrawerListener(actionBarDrawerToggle); 
        actionBarDrawerToggle.syncState(); 

        // to make the Navigation drawer icon always appear on the action bar 
        getSupportActionBar().setDisplayHomeAsUpEnabled(true); 
```

> activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?> 

<!-- the root view must be the DrawerLayout -->
<androidx.drawerlayout.widget.DrawerLayout xmlns:android="http://schemas.android.com/apk/res/android"xmlns:app="http://schemas.android.com/apk/res-auto"xmlns:tools="http://schemas.android.com/tools"
android:id="@+id/my_drawer_layout"android:layout_width="match_parent"android:layout_height="match_parent"
tools:context=".MainActivity"

tools:ignore="HardcodedText"> 

  

    <LinearLayout

        android:layout_width="match_parent"

        android:layout_height="match_parent"> 

  

        <TextView

            android:layout_width="match_parent"

            android:layout_height="wrap_content"

            android:layout_marginTop="128dp"

            android:gravity="center"

            android:text="Home"

            android:textSize="18sp" /> 

    </LinearLayout> 

  

    <!-- this the navigation view which draws and shows the navigation drawer -->

    <!-- include the menu created in the menu folder
            app:menu="@menu/navigation_menu" -->

    <com.google.android.material.navigation.NavigationView

        android:layout_width="wrap_content"

        android:layout_height="match_parent"

        android:layout_gravity="start">
        
        
            <LinearLayout

        android:layout_width="match_parent"
        android:orientation="vertical"

        android:layout_height="match_parent"> 

        
        <TextView

            android:layout_width="match_parent"

            android:layout_height="wrap_content"

            android:padding="8dp"

            android:gravity="center"
android:onClick="onClickButtonClose"
            android:text="Drawer"
            android:textColor="@color/white"
            android:background="@color/primary_material_dark"

            android:textSize="18sp" />
            
        
        <Button

            android:layout_width="match_parent"

            android:layout_height="wrap_content"

            android:padding="8dp"
            android:layout_marginTop="8dp"

            android:gravity="center"
            android:onClick="onClickButton"
            android:text="Click"
            android:textColor="@color/white"
            android:background="@color/primary_material_dark"

            android:textSize="18sp" />
            
                </LinearLayout>
            
    </com.google.android.material.navigation.NavigationView>

  

</androidx.drawerlayout.widget.DrawerLayout>
```