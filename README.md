<form id="form">
  <div class="field">
    <label for="message">message</label>
    <input type="text" name="message" id="message">
  </div>
  <div class="field">
    <label for="email">email</label>
    <input type="text" name="email" id="email">
  </div>

  <input type="submit" id="button" value="Send Email" >
</form>

<script type="text/javascript"
  src="https://cdn.jsdelivr.net/npm/emailjs-com@2/dist/email.min.js"></script>

<script type="text/javascript">
  emailjs.init('user_m7YziIlMKzRBrkMD4OcGH')
</script>
<style type="text/css">
  .field {
  margin-bottom: 10px;
}

.field label {
  display: block;
  font-size: 12px;
  color: #777;
}

.field input {
  display: block;
  min-width: 250px;
  line-height: 1.5;
  font-size: 14px;
}

input[type="submit"] {
  display: block;
  padding: 6px 30px;
  font-size: 14px;
  background-color: #4460AA;
  color: #fff;
  border: none
}
</style>
<script type="text/javascript">
  const btn = document.getElementById('button');

document.getElementById('form')
 .addEventListener('submit', function(event) {
   event.preventDefault();

   btn.value = 'Sending...';

   const serviceID = 'default_service';
   const templateID = 'template_p6tz9gq';

   emailjs.sendForm(serviceID, templateID, this)
    .then(() => {
      btn.value = 'Send Email';
      alert('Sent!');
    }, (err) => {
      btn.value = 'Send Email';
      alert(JSON.stringify(err));
    });
});
</script>
