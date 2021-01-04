---
title: ""
description: "Drop us an email."
date: 2020-08-27T19:25:12+02:00
lastmod: 2020-08-27T19:25:12+02:00
draft: false
images: []
---

<section class="section container-fluid mt-n3 pb-3">
  <div class="row justify-content-center">
    <div class="col-lg-12 text-center">
      <h1 class="mt-0">Get in Touch</h1>
    </div>
    <div class="col-lg-9 col-xl-8 text-center">
        <p class="meta">Send me an Email</p>
    </div>
  </div>
</section>


<form name="contact" method="POST" data-netlify="true">
  <p>
    <label>Your Name: <input type="text" name="name" /></label>   
  </p>
  <p>
    <label>Your Email: <input type="email" name="email" /></label>
  </p>
  <p>
    <label>Message: <textarea name="message"></textarea></label>
  </p>
  <p>
    <button class="btn btn-primary btn-lg px-4 mb-2" type="submit" onclick="handleSubmit()">Send</button>
  </p>
</form>

<script>
function encode(data) {
    return Object.keys(data)
        .map(key => encodeURIComponent(key) + "=" + encodeURIComponent(data[key]))
        .join("&")
  }

const handleSubmit = (event) => {
  event.preventDefault()
  fetch("/", {
    method: "POST",
    headers: { "Content-Type": "application/x-www-form-urlencoded" },
    body: encode({
      "form-name": event.target.getAttribute("name"),
      ...name
    })
  }).then(() => navigate("/")).catch(error => alert(error))
}
</script>
