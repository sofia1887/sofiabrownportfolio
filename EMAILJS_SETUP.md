# EmailJS Setup Guide for Contact Form

## 🚀 **Step 1: Create EmailJS Account**

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" and create your account
3. Verify your email address

## 📧 **Step 2: Set Up Email Service**

1. **Go to "Email Services"** in your EmailJS dashboard
2. **Click "Add New Service"**
3. **Choose your email provider**:
   - **Gmail** (recommended for personal use)
   - **Outlook**
   - **Yahoo**
   - **Custom SMTP**
4. **Follow the setup instructions** for your chosen provider
5. **Copy your Service ID** (you'll need this later)

## 📝 **Step 3: Create Email Template**

1. **Go to "Email Templates"** in your EmailJS dashboard
2. **Click "Create New Template"**
3. **Use this template content**:

```
Subject: New Contact Form Message from {{from_name}}

Hello Sofia,

You have received a new message from your portfolio contact form:

Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your portfolio website.
```

4. **Save the template** and copy the Template ID

## 🔑 **Step 4: Get Your Public Key**

1. **Go to "Account"** → **"General"**
2. **Copy your Public Key** (starts with letters/numbers)

## ⚙️ **Step 5: Update Your Code**

1. **Open `script.js`** in your project
2. **Replace these values**:

```javascript
const EMAILJS_SERVICE_ID = 'YOUR_SERVICE_ID'; // Replace with your Service ID
const EMAILJS_TEMPLATE_ID = 'YOUR_TEMPLATE_ID'; // Replace with your Template ID  
const EMAILJS_PUBLIC_KEY = 'YOUR_PUBLIC_KEY'; // Replace with your Public Key
```

## 🧪 **Step 6: Test Your Contact Form**

1. **Open your portfolio website**
2. **Go to the contact section**
3. **Fill out the form** with test data
4. **Submit the form**
5. **Check your email** for the message

## 📋 **Step 7: Configure Email Settings (Optional)**

### **Gmail Setup:**
1. **Enable 2-Factor Authentication** on your Gmail account
2. **Generate App Password**:
   - Go to Google Account settings
   - Security → 2-Step Verification → App passwords
   - Generate password for "Mail"
3. **Use the app password** in EmailJS service setup

### **Email Limits:**
- **Free Plan**: 200 emails/month
- **Paid Plans**: Higher limits available
- **Rate Limiting**: 10 emails/minute on free plan

## 🔧 **Troubleshooting**

### **Common Issues:**
1. **"Service not found"**: Check your Service ID
2. **"Template not found"**: Check your Template ID
3. **"Invalid public key"**: Check your Public Key
4. **"Email not sending"**: Check your email service configuration

### **Debug Steps:**
1. **Check browser console** for error messages
2. **Verify all IDs** are correct
3. **Test with simple template** first
4. **Check email service** is properly configured

## ✅ **Your Contact Form is Ready!**

Once configured, your contact form will:
- ✅ **Send emails directly** to your inbox
- ✅ **Include all form data** (name, email, subject, message)
- ✅ **Work without backend** server
- ✅ **Handle errors gracefully** with user feedback
- ✅ **Reset form** after successful submission

## 🎯 **Benefits of EmailJS:**
- **No Backend Required**: Works with static websites
- **Easy Setup**: Simple configuration
- **Reliable**: Professional email delivery
- **Free Tier**: 200 emails/month
- **Real-time**: Instant email delivery

**Follow these steps and your contact form will be fully functional!**
