<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
  <div class="text-center"> 
    <h1 class="display-4">Welcome</h1>
    <fb:login-button 
      scope="public_profile,email"
      onlogin="checkLoginState();">
    </fb:login-button>
    <div id="authStatus"></div>
  </div>
 
 <script>
    window.fbAsyncInit = function() {
      FB.init({
        appId      : '664086267548417',
        cookie     : true,
        xfbml      : true,
        version    : 'v8.0'
      });
        
      FB.AppEvents.logPageView();   
        
    };

    (function(d, s, id){
      var js, fjs = d.getElementsByTagName(s)[0];
      if (d.getElementById(id)) {return;}
      js = d.createElement(s); js.id = id;
      js.src = "https://connect.facebook.net/en_US/sdk.js";
      fjs.parentNode.insertBefore(js, fjs);
    }(document, 'script', 'facebook-jssdk'));

    function  checkLoginState(){

      FB.getLoginStatus(function(response) {
        console.log(JSON.stringify(response, null, 2));
        $("#authStatus").html("<code>" + JSON.stringify(response, null, 2) + "</code>");
      });
    }

  </script>
</body>
</html>
