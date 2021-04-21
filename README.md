# Response-timer
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>ITS MY GAME!!</title>
    <style media="screen">
      #box{
        width:200px;
        height:200px;
        background-color:red;
        display:none;
        position: relative;
      }
    </style>
  </head>
  <body>
    <h1>The Response Game!</h1>
    <p><em>Test your reaction</em></p>
    <p>You took <span id='time'></span> seconds!!</p>
    <div id="box">

    </div>
    <script type="text/javascript">
      var clicktime; var createdtime; var responsetime;
      function randomcolor(){
      var temp="0123456789abcdef".split('');
      var color="#";
      for(var i=0;i<6;i++){
        color=color+temp[Math.round(Math.random()*15)];
      }
      return(color);
    }
      function makebox(){

        var time;
        time=Math.random();
        time=time*5000;
        setTimeout(function (){
          var top; var left;
          top=Math.random();
          top=top*300;
          left=Math.random();
          left=left*300;
          document.getElementById('box').style.left=left+"px";
          document.getElementById('box').style.top=top+"px";
          document.getElementById('box').style.backgroundColor=randomcolor();
          if(Math.random()>0.5){
            document.getElementById("box").style.borderRadius="100px";
          }else{
            document.getElementById("box").style.borderRadius="0";
          }
          document.getElementById("box").style.display="block";

          createdtime=Date.now();
        },time);

      }
      makebox();
      document.getElementById('box').onclick=function(){
        clicktime=Date.now();
        responsetime=[clicktime-createdtime]/1000;
        document.getElementById('time').innerHTML=responsetime;
        document.getElementById('box').style.display='none';
        makebox();
      }
    </script>
  </body>
</html>
 
