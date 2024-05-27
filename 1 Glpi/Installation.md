This was a job task, install the new **GLPI** version, v 10.0.15, I did it our **Kubernetes** cluster.

# Auto-login

The super **interesting** part was understand how to perform the auto-login phase, as the new version of **GLPI** implement an application **router** to decide what page the user can see, the login.php was not accessible without visiting first the index page.

For now I implemented the auto-login via the following javascript snippet

```javascript
$(function () {
  const currentUrl = new URL(window.location.href);
  const currentParams = new URLSearchParams(currentUrl.search);
  const token = currentParams.get('token');
  
  if (token) {
    // parse the token phase

    const loginName = document.getElementById('login_name');
    const loginPassword = document.getElementById('login_password');
    const glpiForm = document.getElementById('glpi_form');

    if (tokenData.name && tokenData.password) {
      loginName.value = tokenData.name;
      loginPassword.value = tokenData.password;
      glpiForm.submit.click();
    }
  }
});
```

It is not the best solution but for now it works.

Our **Single Sign On** call the GLPI instance with a token, in the twig template I managed to get the token, parse it and did the form submit programmatically.
