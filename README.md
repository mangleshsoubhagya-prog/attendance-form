<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Installation Entry</title>
</head>
<body>

<h2>Installation Entry</h2>

<input type="datetime-local" id="installDate"><br><br>
<input id="indusId" placeholder="Indus ID"><br><br>
<input id="engineer1" placeholder="Engineer Name"><br><br>
<input id="wire" placeholder="Wire Used"><br><br>
<input id="district" placeholder="District"><br><br>
<textarea id="remarks" placeholder="Remarks"></textarea><br><br>
<input id="engineer2" placeholder="Engineer Name 2"><br><br>
<input id="sensor" placeholder="Sensor No"><br><br>

<button onclick="submitForm()">Submit</button>

<script>

const WEB_APP_URL="https://script.google.com/macros/s/AKfycbyy59mpAWgxq5I6gJUQEzfKKfbx1akFL211NaFJzcKJxGLlOWogx9q29wp9EpkRHw5f/exec%22";

function submitForm(){

let data = new URLSearchParams();

data.append("installDate", document.getElementById("installDate").value);
data.append("indusId", document.getElementById("indusId").value);
data.append("engineer1", document.getElementById("engineer1").value);
data.append("wire", document.getElementById("wire").value);
data.append("district", document.getElementById("district").value);
data.append("remarks", document.getElementById("remarks").value);
data.append("engineer2", document.getElementById("engineer2").value);
data.append("sensor", document.getElementById("sensor").value);

fetch(WEB_APP_URL,{
method:"POST",
body:data
})
.then(res=>res.text())
.then(msg=>{
alert("Saved Successfully ✅");
})
.catch(err=>{
alert("Error: "+err);
});

}

</script>

</body>
</html>
