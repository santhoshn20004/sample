<!DOCTYPE html>
<html>
<style>
input[type=text], select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type=submit] {
  width: 100%;
  background-color: #4CAF50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type=submit]:hover {
  background-color: #45a049;
}

div {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>
<body>

<h3>Go off the roads...</h3>

<div>
  <form method="POST" name="google-sheet">
    <label for="name">Name of the passenger </label>
    <input type="text" id="fname" name="Name" placeholder="Your name..">

    <label for="email"> Email </label>
    <input type="text" id="lname" name="Email" placeholder="Your Email..">

    <label for="mobile"> Phone Number</label>
    <input type="text" id="lname" name="Phone Number" placeholder="Your contact..">
  
    <input type="submit" value="Submit"name="submit">
  </form>
</div>

         <script>
            const scriptURL = 'https://script.google.com/macros/s/AKfycbyQUeU4VKxSv6Cvox-aI-bMxrTfewCzg1Gv1gOzPYL8GpwUpA9cYEch4O9ucLGbWl83aA/exec'
            const form = document.forms['google-sheet']
          
            form.addEventListener('submit', e => {
              e.preventDefault()
              fetch(scriptURL, { method: 'POST', body: new FormData(form)})
                .then(response => alert("Thank you...! Enjoy your delightful journey with JKS..."))
                .catch(error => console.error('Error!', error.message))
            })
          </script>


</body>
</html>

