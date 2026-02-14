# attendance-form<script>

const WEB_APP_URL="https://script.google.com/macros/s/AKfycbyy59mpAWgxq5I6gJUQEzfKKfbx1akFL211NaFJzcKJxGLlOWogx9q29wp9EpkRHw5f/exec";

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
.then(res => res.text())
.then(msg => {

alert("Saved Successfully ✅");

/* Form Clear */
document.querySelectorAll("input, textarea").forEach(e=>e.value="");

})
.catch(err=>{
alert("Error: "+err);
});

}

</script>
