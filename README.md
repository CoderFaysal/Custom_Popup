# Custom Popup

## Create a XML Layout File 

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:id="@+id/dialog_lay_all"
    android:padding="15dp"
    android:background="#FFFFFF"
    >

    <ImageView
        android:id="@+id/tvThanks"
        android:layout_width="40dp"
        android:layout_height="40dp"
        android:src="@drawable/ic_close"
        android:clickable="true"
        android:foreground="?attr/selectableItemBackgroundBorderless"
        android:padding="5dp"
        android:tag="okay"
        android:layout_alignParentEnd="true"
        />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:gravity="center"
        >

        <com.airbnb.lottie.LottieAnimationView
            android:layout_width="match_parent"
            android:layout_height="100dp"
            android:scaleType="centerInside"
            app:lottie_autoPlay="true"
            app:lottie_loop="true"
            app:lottie_rawRes="@raw/done"
            app:lottie_repeatMode="restart"
            android:layout_marginTop="12dp"
            />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Good Job ! Dear"
            android:textColor="@color/black"
            android:textSize="20sp"
            android:textStyle="bold"
            android:layout_marginTop="20dp"
            android:textAlignment="center"
            />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Post has been completed successfully"
            android:textColor="@color/black"
            android:textSize="17sp"
            android:layout_marginTop="13dp"
            android:textAlignment="center"
            />


    </LinearLayout>

</RelativeLayout>
```


## JAVA Create a Function

```
private void customPopup(){

        Handler handler = new Handler(Looper.getMainLooper());
        handler.postDelayed(new Runnable() {
            @Override
            public void run() {

                final Dialog dialog = new Dialog(MainActivity.this);
                dialog.requestWindowFeature(Window.FEATURE_NO_TITLE);
                dialog.setCancelable(true);
                dialog.setContentView(R.layout.dialog_popup);
                dialog.show();
                ImageView tvThanks = dialog.findViewById(R.id.tvThanks);
                tvThanks.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View view) {
                        dialog.dismiss();
                    }
                });

            }
        }, 2000);

    }
```


## Button Click

```
customPopup();
```




