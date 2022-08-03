 <script src="https://unpkg.com/launchdarkly-js-client-sdk@2"></script>
<h1> Gitworkflow - ch04 - TBD <h1>

<p/>
<p/>
<p/>

<div> 
  <p>GitHub workflow 1<p> 
  <p>GitHub workflow 2<p> 
<div>

<div id = "preview" style = "display:none"> 
  <p>GitHub workflow 3<p> 
<div>

<script> 
  
  var clientId = "62e938a6466c5d12398b83a1"; 
  var flagName = "git-wrkflw-preview";
  
  var user = { anonymous: true }; 
  var ldclient = window.LDClient.initialize(clientId, user); 
  
  ldclient.on("ready", function() { 
    document.getElementById("preview").style.display = ldclient.variation(flagName, false) ? "block":"none"; 
    }); 

  ldclient.on("change:" + flagName, function(newVal, prevVal) {
     document.getElementById("preview").style.display = newVal ? "block":"none"; 
      }); 
  
  </script>
