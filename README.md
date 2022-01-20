- 👋 Hi, I’m @rasheedmohammedmansuri
- 👀On Create ( Initialisation )

registerReceiver(SongDataReceiver,new IntentFilter("com.dplay.SONG_DATA"));

registerReceiver(SongStateReceiver,new IntentFilter("com.dplay.SONG_STATE"));
More Block ( Receive )

Allign asd blocks as shown bellow



ASD 1

}
private BroadcastReceiver SongDataReceiver = new BroadcastReceiver() {
      @Override
      public void onReceive(Context context, Intent intent) {

duration = intent.getStringExtra("total_duration");
current = intent.getStringExtra("current_duration");
// Your Seekbar and Time textview

ASD 2

}
   };
private BroadcastReceiver SongStateReceiver = new BroadcastReceiver() {
      @Override
      public void onReceive(Context context, Intent intent) {
state = intent.getStringExtra("responce");
// Set button state ( Pause or playing )

ASD 3

}
   };
{
Start or Stop Service

if(button1.getText().equals("Start"))
{
Intent myService = new Intent(MainActivity.this, DreamPLAYBackgroundMusic.class);
myService.putExtra("url", url);
startService(myService);
button1.setText("Stop");
                   
}else {

Intent myService = new Intent(MainActivity.this, DreamPLAYBackgroundMusic.class);
stopService(myService);
button1.setText("Start");
                    
}
PLAY / PAUSE button

Intent intent=new Intent("com.dplay.SONG_CONTROL");
intent.putExtra("data", "playpause");
sendBroadcast(intent);
REQUEST State : ( Get playing or paused )

Intent intent=new Intent("com.dplay.SONG_STATE");
intent.putExtra("data", "state");
sendBroadcast(intent);
SEEK BAR on stop touch : ( To seek music )

Intent intent=new Intent("com.dplay.SONG_SEEK");
intent.putExtra("data", pos);
sendBroadcast(intent);
// pos is a string variable which we need to assign cureent Seekbar position

Andorid manifest

<service
    android:name="DreamPLAYBackgroundMusic" >
</service>






WATCH VIDEO ON YOUTUBE WATCH
 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
rasheedmohammedmansuri/rasheedmohammedmansuri is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
