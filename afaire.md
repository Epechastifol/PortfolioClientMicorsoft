Pour recevoir les infos de votre page contact par email sur un site statique, voici les solutions possibles :

## 🚨 **Solution recommandée : Service tiers**

### 1. **Netlify Forms** (Gratuit)
```html
<form name="contact" method="POST" data-netlify="true" netlify>
  <input type="text" name="name" placeholder="Votre nom" required>
  <input type="email" name="email" placeholder="Votre email" required>
  <textarea name="message" placeholder="Votre message" required></textarea>
  <button type="submit">Envoyer</button>
</form>
```

### 2. **Formspree** (Gratuit)
```html
<form action="https://formspree.io/f/your-form-id" method="POST">
  <input type="text" name="name" required>
  <input type="email" name="email" required>
  <textarea name="message" required></textarea>
  <button type="submit">Envoyer</button>
</form>
```

### 3. **FormSubmit** (Gratuit)
```html
<form action="https://formsubmit.io/send/votre@email.com" method="POST">
  <input name="name" type="text" required>
  <input name="email" type="email" required>
  <textarea name="message" required></textarea>
  <button type="submit">Envoyer</button>
</form>
```

## 🔧 **Solution technique : Google Apps Script**

1. **Créez un script Google Apps Script**
```javascript
function doPost(e) {
  var data = e.parameter;
  var email = data.email;
  var name = data.name;
  var message = data.message;
  
  MailApp.sendEmail({
    to: "votre@email.com",
    subject: "Nouveau message de " + name,
    body: "De: " + name + " (" + email + ")\n\nMessage:\n" + message
  });
  
  return ContentService.createTextOutput("Success");
}
```

2. **Votre formulaire HTML**
```html
<form action="VOTRE_URL_SCRIPT" method="POST">
  <input type="text" name="name" placeholder="Nom" required>
  <input type="email" name="email" placeholder="Email" required>
  <textarea name="message" placeholder="Message" required></textarea>
  <button type="submit">Envoyer</button>
</form>
```

## 📝 **Exemple complet avec Formspree**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Contact</title>
    <style>
        .contact-form {
            max-width: 500px;
            margin: 0 auto;
            padding: 20px;
        }
        .form-group {
            margin-bottom: 15px;
        }
        input, textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            background: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <form class="contact-form" action="https://formspree.io/f/your-form-id" method="POST">
        <div class="form-group">
            <input type="text" name="name" placeholder="Votre nom" required>
        </div>
        <div class="form-group">
            <input type="email" name="email" placeholder="Votre email" required>
        </div>
        <div class="form-group">
            <textarea name="message" rows="5" placeholder="Votre message" required></textarea>
        </div>
        <button type="submit">Envoyer le message</button>
    </form>
</body>
</html>
```

## 🎯 **Recommandation**

Je recommande **Formspree** ou **Netlify Forms** car :
- ✅ **Gratuit** pour un usage basique
- ✅ **Simple** à mettre en place
- ✅ **Sécurisé**
- ✅ **Pas de backend** nécessaire
- ✅ **Notifications** par email

## 📋 **Étapes pour Formspree**

1. Allez sur [formspree.io](https://formspree.io)
2. Créez un compte gratuit
3. Obtenez votre URL de formulaire
4. Copiez-collez le code HTML dans votre site
5. Testez le formulaire

Avez-vous besoin d'aide pour configurer l'une de ces solutions ?