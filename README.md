# CustomCornerCircularView
This library provides you a dynamic rotating circular menu at any corner to select and start your next activity with the help of Intent.

To get a Git project into your build:

Step 1. Add the JitPack repository to your build file

Add it in your root build.gradle at the end of repositories:

    allprojects {
      repositories {
        ...
        maven { url 'https://jitpack.io' }
      }
    }

Step 2. Add the dependency

    dependencies {
              implementation 'com.github.AndroidDevelopers97:CustomCornerCircularView:1.0.0'
    }

Step 3. Add the following tag of CornerCircularView in your xml file

For example:-

     <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MainActivity">

      <com.ad97.cccv.CustomCornerCircularView
          android:id="@+id/cccv"
          android:layout_width="match_parent"
          android:layout_height="match_parent"
          app:corner_side="bottom_right"/>

    </RelativeLayout>

Step 4. Add the following code to your activity.java file

    import ..

    import com.ad97.cccv.CustomCornerCircularView;
    import com.ad97.cccv.ModelInfo;


    public class MainActivity extends AppCompatActivity {
        private CustomCornerCircularView cornerCircularView;
        private List<ModelInfo> modelInfo;
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);
            cornerCircularView = findViewById(R.id.cccv);
            modelInfo = new ArrayList<>();

            // adding information of the item to get menu on screen with these added items
            modelInfo.add(new ModelInfo("Message", Color.RED,R.drawable.message,R.color.colorAccent,null ));
            modelInfo.add(new ModelInfo("Mic",Color.BLUE,R.drawable.mic,R.color.colorPrimary,null ));
            modelInfo.add(new ModelInfo("Photo",Color.MAGENTA,R.drawable.photo,R.color.colorPrimaryDark,null ));
            modelInfo.add(new ModelInfo("Settings",Color.BLACK,R.drawable.settings,R.color.colorAccent,
                    new Intent(MainActivity.this,NextActivity.class).putExtra("type","Settings")));

            // setting menu items from our itemList (modelInfo)
            cornerCircularView.setMenuFromList(modelInfo);
            // setting addButton color according to our choice
            cornerCircularView.setAddButtonColor(Color.BLACK);
        }
    }


<a href="https://imgflip.com/gif/2gxkoi"><img src="https://i.imgflip.com/2gxkoi.gif" title="made at imgflip.com"/></a>
<a href="https://imgflip.com/gif/2gxktq"><img src="https://i.imgflip.com/2gxktq.gif" title="made at imgflip.com"/></a>
<a href="https://imgflip.com/gif/2gxkrc"><img src="https://i.imgflip.com/2gxkrc.gif" title="made at imgflip.com"/></a>
<a href="https://imgflip.com/gif/2gxkv6"><img src="https://i.imgflip.com/2gxkv6.gif" title="made at imgflip.com"/></a>


