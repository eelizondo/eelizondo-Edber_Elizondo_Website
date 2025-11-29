# EmailJS Contact Form Setup Guide

## Overview
Your contact form is now configured to use EmailJS, a free service that sends emails directly from the browser without needing a backend server.

## Setup Steps

### 1. Create EmailJS Account
1. Go to https://www.emailjs.com/
2. Click "Sign Up" and create a free account
3. Verify your email address

### 2. Add Email Service
1. In your EmailJS dashboard, go to **Email Services**
2. Click **Add New Service**
3. Choose your email provider (Gmail recommended)
4. Follow the instructions to connect your email
5. Copy the **Service ID** (you'll need this)

### 3. Create Email Template
1. Go to **Email Templates** in the dashboard
2. Click **Create New Template**
3. Use this template structure:

```
Subject: New Contact Form Submission from {{user_email}}

From: {{user_email}}

Message:
{{message}}
```

4. Save the template and copy the **Template ID**

### 4. Get Your Public Key
1. Go to **Account** → **General**
2. Copy your **Public Key**

### 5. Update Your Website
Open `Edber Elizondo - Website.html` and find these three places to update:

```javascript
emailjs.init("YOUR_PUBLIC_KEY"); // Replace with your Public Key

emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', this)
//                ^^^^^^^^^^^^^^^^   ^^^^^^^^^^^^^^^^^^
//                Replace these with your Service ID and Template ID
```

**Example:**
```javascript
emailjs.init("abcD1234EfGh567IJ"); 

emailjs.sendForm('service_xyz123', 'template_abc456', this)
```

### 6. Test Your Form
1. Open your website
2. Fill out the contact form
3. Click "Send Message"
4. Check your email inbox for the message

## Features Included

✅ **Loading State** - Button shows "Sending..." while processing
✅ **Success Message** - Green confirmation when email is sent
✅ **Error Handling** - Red error message if something goes wrong
✅ **Form Reset** - Clears fields after successful submission
✅ **Validation** - Both fields are required
✅ **Disabled State** - Prevents multiple submissions

## EmailJS Free Tier
- 200 emails/month
- No credit card required
- Perfect for personal websites

## Troubleshooting

**Form not sending?**
- Check browser console for errors (F12)
- Verify all three IDs are correct (Public Key, Service ID, Template ID)
- Make sure you're connected to the internet
- Check EmailJS dashboard for error logs

**Need more emails per month?**
- EmailJS paid plans start at $7/month for 1000 emails

## Alternative: Direct Email Link
If you prefer not to use EmailJS, you can replace the form with a simple mailto link:

```html
<a href="mailto:edber.elizondo@gmail.com?subject=Project Inquiry" 
   class="inline-block px-8 py-4 bg-cyan-500 text-slate-950 font-semibold rounded-xl hover:bg-cyan-400 transition-all">
    Send Me an Email
</a>
```

---

For questions or issues, visit: https://www.emailjs.com/docs/
