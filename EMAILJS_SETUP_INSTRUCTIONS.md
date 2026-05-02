# EmailJS Setup Instructions

Your contact form is now configured to send emails using EmailJS! Follow these steps to complete the setup:

## Step 1: Create EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" and create a free account
3. Verify your email address

## Step 2: Add Email Service

1. In your EmailJS dashboard, go to **Email Services**
2. Click **Add New Service**
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the connection instructions
5. Copy your **Service ID** (e.g., `service_abc1234`)

## Step 3: Create Email Template

1. Go to **Email Templates** in the dashboard
2. Click **Create New Template**
3. Use this template structure:

```
Subject: {{subject}}

From: {{from_name}}
Email: {{from_email}}

Message:
{{message}}
```

4. Save the template and copy your **Template ID** (e.g., `template_xyz5678`)

## Step 4: Get Your Public Key

1. Go to **Account** → **General**
2. Find your **Public Key** (e.g., `AbCdEfGhIjKlMnOp`)

## Step 5: Update Your Code

Open `js/main.js` and replace these values on lines 69-71:

```javascript
const EMAILJS_PUBLIC_KEY = 'YOUR_PUBLIC_KEY';     // Replace with your Public Key
const EMAILJS_SERVICE_ID = 'YOUR_SERVICE_ID';     // Replace with your Service ID
const EMAILJS_TEMPLATE_ID = 'YOUR_TEMPLATE_ID';   // Replace with your Template ID
```

## Step 6: Test Your Form

1. Open your portfolio website
2. Go to the Contact page
3. Fill out the form and click "Send Message"
4. Check your email inbox for the message!

## Template Variables Used

The form sends these variables to EmailJS:
- `from_name` - Visitor's name
- `from_email` - Visitor's email
- `subject` - Message subject
- `message` - Message content

Make sure your EmailJS template includes these variables using `{{variable_name}}` syntax.

## Free Tier Limits

EmailJS free plan includes:
- 200 emails per month
- 2 email templates
- 1 email service

This should be sufficient for a portfolio website!

## Troubleshooting

**Form not sending?**
- Check browser console for errors
- Verify all three IDs are correctly entered
- Make sure EmailJS service is connected
- Check your monthly email limit

**Not receiving emails?**
- Check spam/junk folder
- Verify email service connection in EmailJS dashboard
- Test the template in EmailJS dashboard first

## Alternative: Direct Email Link

If you prefer not to use EmailJS, you can change the form to open the user's email client:

```html
<a href="mailto:trishacaisipl@gmail.com?subject=Project%20Inquiry" class="submit-btn">
    Send Email
</a>
```

---

**Need help?** Check EmailJS documentation: https://www.emailjs.com/docs/
