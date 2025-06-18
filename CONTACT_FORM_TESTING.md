# Contact Form Testing Guide

## ✅ Contact Form Functionality Testing

### 🔧 **Setup Requirements**

Before testing the email functionality, configure your `.env` file:

```env
# Email Server Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_SECURE=false
EMAIL_USER=your-email@greanworld.com
EMAIL_PASS=your-app-password

# Email Recipients
EMAIL_TO=info@greanworld.com,sileshi@greanworld.com
EMAIL_FROM=noreply@greanworld.com
EMAIL_REPLY_TO=info@greanworld.com

# Email Templates
EMAIL_SUBJECT_PREFIX=[GREAN WORLD Contact]
```

### 📋 **Test Scenarios**

#### 1. **Form Validation Tests**

**Test Case 1: Empty Form Submission**

- Leave all fields empty
- Click "Send Message"
- **Expected**: Error message showing all required fields

**Test Case 2: Invalid Email Format**

- Fill name: "John Doe"
- Fill email: "invalid-email"
- Fill other required fields
- **Expected**: "Please enter a valid email address" error

**Test Case 3: Short Name**

- Fill name: "A"
- Fill other fields correctly
- **Expected**: "Name must be at least 2 characters long" error

**Test Case 4: Short Subject**

- Fill subject: "Hi"
- Fill other fields correctly
- **Expected**: "Subject must be at least 3 characters long" error

**Test Case 5: Short Message**

- Fill message: "Hello"
- Fill other fields correctly
- **Expected**: "Message must be at least 10 characters long" error

**Test Case 6: No Interest Selected**

- Fill all fields except "I'm Interested In"
- **Expected**: "Please select what you are interested in" error

#### 2. **Successful Submission Tests**

**Test Case 7: Valid Form Submission**

- Fill all required fields correctly:
  - Name: "John Doe"
  - Email: "john@example.com"
  - Subject: "Solar Energy Inquiry"
  - Interest: "Solar Energy Solutions"
  - Message: "I'm interested in solar panels for my home."
- **Expected**:
  - Success message appears
  - Form resets automatically
  - Email sent to team
  - Auto-reply sent to customer

#### 3. **Error Handling Tests**

**Test Case 8: Network Error Simulation**

- Disconnect internet
- Submit valid form
- **Expected**: "Network connection error" message

**Test Case 9: Invalid Email Configuration**

- Use incorrect email credentials in .env
- Submit valid form
- **Expected**: "Email service configuration error" message

#### 4. **User Experience Tests**

**Test Case 10: Loading State**

- Submit form and observe button
- **Expected**: Button shows "Sending..." with spinner

**Test Case 11: Message Dismissal**

- Submit form successfully
- Click X button on success message
- **Expected**: Message disappears

**Test Case 12: Auto-hide Success Message**

- Submit form successfully
- Wait 10 seconds
- **Expected**: Success message automatically disappears

### 🎯 **Dropdown Options Testing**

Verify all dropdown options work:

- "Solar Energy Solutions"
- "Clean Cooking Stoves"
- "Energy Consulting"
- "Business Partnership"
- "General Inquiry"

### 📧 **Email Testing**

#### Team Email Should Include:

- Professional HTML template with GREAN WORLD branding
- All form data (name, email, phone, subject, interest, message)
- Timestamp and source information
- Action reminder for 24-hour response

#### Customer Auto-Reply Should Include:

- Thank you message with customer's name
- Confirmation of interest area
- Submission summary
- Contact information
- Professional GREAN WORLD branding

### 🚨 **Security Testing**

**Test Case 13: Spam Detection**

- Submit form with suspicious content (URLs, spam keywords)
- **Expected**: "Suspicious content" error message

**Test Case 14: XSS Prevention**

- Try submitting HTML/JavaScript in form fields
- **Expected**: Content should be sanitized

### 📱 **Responsive Testing**

Test form on different screen sizes:

- Mobile (320px - 768px)
- Tablet (768px - 1024px)
- Desktop (1024px+)

### 🎨 **Theme Testing**

Test form in both themes:

- Light mode
- Dark mode

Verify:

- All colors are appropriate
- Text is readable
- Form fields are properly styled
- Success/error messages are visible

### ⚡ **Performance Testing**

- Form should load quickly
- Validation should be instant
- Submission should complete within 5 seconds
- No memory leaks on repeated submissions

### 🔍 **Accessibility Testing**

- All form fields have proper labels
- Form can be navigated with keyboard
- Screen readers can read all content
- Error messages are announced
- Success messages are announced

## 🎉 **Expected Results**

✅ **Working Contact Form** with:

- Client-side validation with detailed error messages
- Server-side validation and security
- Professional email templates
- Auto-reply functionality
- Loading states and user feedback
- Theme-aware styling
- Mobile responsiveness
- Accessibility compliance
- Spam protection
- Error handling for all scenarios

## 📞 **Fallback Contact Methods**

If form fails, users are directed to:

- **Phone**: (+251) 913 330000 | (+251) 910 212989
- **Email**: info@greanworld.com | sileshi@greanworld.com
- **Office Hours**: Monday - Friday, 8:00 AM - 5:00 PM
