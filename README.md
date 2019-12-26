# Android Mpesa Daraja API library



Project setup 
1. add this in build.gradle   
     ```gradle
     allprojects  { 
		  repositories {
			  ...
			  maven { url 'https://jitpack.io' }
		 }
  	   } 
       
  2.  add the dependency
         ```gradle
      dependencies {
	        implementation 'com.github.ngangavic:androidmpesaapi:v1.0.2'
	     }
  
  3. add the internet permission 
      ```xml
       <uses-permission android:name="android.permission.INTERNET"/>
       
  4. enable strict mode
      ```java
      int SDK_INT = android.os.Build.VERSION.SDK_INT;
        if (SDK_INT > 8) {
            StrictMode.ThreadPolicy policy = new StrictMode.ThreadPolicy.Builder()
                    .permitAll().build();
            StrictMode.setThreadPolicy(policy);
        }
  
  
### Lipa Na Mpesa Online
1. set the environment

        ```
        LNMPSettings.setBusiness_short_code("174379");
        LNMPSettings.setCallback_url("http://smartforex.co.ke/android/mpesa/listener.php");
        LNMPSettings.setConsumer_key("AL4cs1jYio03B97Bvri5SWaPsQ1upawY");
        LNMPSettings.setConsumer_secret("tIO5wyY43Gobzt6C");
        LNMPSettings.setPhone("254708374149");
        LNMPSettings.setStk_push_url("https://sandbox.safaricom.co.ke/mpesa/stkpush/v1/processrequest");
        LNMPSettings.setTimeout_url("http://smartforex.co.ke/android/mpesa/timeout.php");
        LNMPSettings.setTransaction_desc("testing my api");
        LNMPSettings.setTransaction_type("CustomerPayBillOnline");
        LNMPSettings.setAmount("1");
        LNMPSettings.setAccess_token_url("https://sandbox.safaricom.co.ke/oauth/v1/generate?grant_type=client_credentials");
        LNMPSettings.setAccount_reference("vic10020");
        LNMPSettings.setPasskey("bfb279f9aa9bdbcf158e97dd71a467cd2e0c893059b10f78e6b72ada1ed2c919");
        
2. call the verification method

     ```java
     if (stkPush().equals("0")){
         Toast.makeText(MainActivity.this,"Success",Toast.LENGTH_LONG).show();
     }else{
         Toast.makeText(MainActivity.this,"Error",Toast.LENGTH_LONG).show();
     }
    




Sample Activity file [MainActivity.java](https://gist.github.com/ngangavic/d0a70ca89f320ee77f98d68e8a332c1c).
