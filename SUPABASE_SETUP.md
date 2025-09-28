# Supabase Setup Guide for Portfolio Contact Form

## 🚀 **Step 1: Create Supabase Project**

1. Go to [supabase.com](https://supabase.com)
2. Sign up/Login to your account
3. Click "New Project"
4. Choose your organization
5. Enter project details:
   - **Name**: `sofia-portfolio`
   - **Database Password**: Create a strong password
   - **Region**: Choose closest to your location
6. Click "Create new project"
7. Wait for the project to be set up (2-3 minutes)

## 📊 **Step 2: Create Database Table**

1. Go to your Supabase dashboard
2. Click on "SQL Editor" in the left sidebar
3. Click "New query"
4. Copy and paste this SQL code:

```sql
-- Create contact_messages table
CREATE TABLE contact_messages (
    id BIGSERIAL PRIMARY KEY,
    name TEXT NOT NULL,
    email TEXT NOT NULL,
    subject TEXT NOT NULL,
    message TEXT NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Enable Row Level Security (RLS)
ALTER TABLE contact_messages ENABLE ROW LEVEL SECURITY;

-- Create policy to allow inserts (anyone can submit contact form)
CREATE POLICY "Allow public inserts" ON contact_messages
    FOR INSERT WITH CHECK (true);

-- Create policy to allow reads (you can view messages)
CREATE POLICY "Allow authenticated reads" ON contact_messages
    FOR SELECT USING (auth.role() = 'authenticated');
```

5. Click "Run" to execute the SQL

## 🔑 **Step 3: Get Your API Keys**

1. In your Supabase dashboard, go to "Settings" → "API"
2. Copy these values:
   - **Project URL** (looks like: `https://your-project-id.supabase.co`)
   - **anon public** key (starts with `eyJ...`)

## ⚙️ **Step 4: Update Your Code**

1. Open `script.js` in your project
2. Find these lines:
   ```javascript
   const supabaseUrl = 'YOUR_SUPABASE_URL';
   const supabaseKey = 'YOUR_SUPABASE_ANON_KEY';
   ```
3. Replace with your actual values:
   ```javascript
   const supabaseUrl = 'https://your-project-id.supabase.co';
   const supabaseKey = 'your-anon-key-here';
   ```

## 📧 **Step 5: Test the Form**

1. Open your portfolio website
2. Go to the contact section
3. Fill out the form and submit
4. Check your Supabase dashboard → "Table Editor" → "contact_messages"
5. You should see the submitted data!

## 🔒 **Step 6: Set Up Email Notifications (Optional)**

To get notified when someone submits the form:

1. Go to "Database" → "Functions" in Supabase
2. Create a new function for email notifications
3. Or use Supabase Edge Functions for more advanced email handling

## 📱 **Step 7: View Messages**

1. Go to your Supabase dashboard
2. Click "Table Editor"
3. Select "contact_messages" table
4. View all submitted contact form messages
5. You can export data as CSV if needed

## 🛠️ **Troubleshooting**

### If form doesn't work:
- Check browser console for errors (F12)
- Verify your Supabase URL and key are correct
- Make sure the table was created successfully

### If you can't see messages:
- Check that RLS policies are set up correctly
- Verify you're logged into Supabase dashboard
- Check the table name matches exactly: `contact_messages`

## 🎉 **You're Done!**

Your contact form now stores all submissions in Supabase database. You can view, manage, and export all contact form submissions from your Supabase dashboard!
