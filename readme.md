# **Django Authentication System**

This is a Django-based web application that provides a complete user authentication system, including login
## **Features**

1. **User Authentication**
   - Login with email or username and password.
   - Sign up with a username, email, and password.

2. **Password Management**
   - Password reset via email with secure token-based links.
   - Change password for authenticated users.

3. **Dashboard**
   - Accessible only to authenticated users.
   - Personalized greeting with the option to navigate to profile or logout.

4. **Profile Page**
   - Displays user details such as username, email, date joined, and last updated.

5. **Access Restrictions**
   - Certain pages are restricted based on authentication status.

---

## **Setup and Installation**

### **1. Clone the Repository**
```bash
git clone https://github.com/Shivansh-Ahirwal/Django-Authentication-System.git
cd Django-Authentication-System
```

### **2. Create a Virtual Environment**
```bash
python -m venv venv
source venv/bin/activate  # For Linux/MacOS
venv\Scripts\activate     # For Windows
```

### **3. Install Requirements**
```bash
pip install -r requirements.txt
```

### **4. Configure the Database**
By default, the project uses SQLite. To set up the database:
```bash
python manage.py migrate
```

### **5. Create a Superuser**
To access the admin panel and manage users:
```bash
python manage.py createsuperuser
```

### **6. Run the Development Server**
```bash
python manage.py runserver
```
Visit `http://127.0.0.1:8000/` in your browser.

---

## **Configuration**

### **Email Setup**
To enable password reset functionality, configure your email backend in `settings.py`:

#### Using Gmail SMTP:
```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'your_email@gmail.com'  # Replace with your email
EMAIL_HOST_PASSWORD = 'your_password'    # Replace with your password
```

#### Testing Locally (Console Backend):
```python
EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'
```
With this setting, reset emails are displayed in the console instead of being sent.

---

## **Project Structure**

```plaintext
├── authentication_system/
│   ├── settings.py         # Django settings
│   ├── urls.py             # Project URLs
│   ├── wsgi.py             # WSGI application
├── templates/              # HTML templates
│   ├── base.html           # Base template for all pages
│   ├── login.html          # Login page
│   ├── signup.html         # Signup page
│   ├── dashboard.html      # Dashboard for authenticated users
│   ├── profile.html        # User profile page
│   ├── password_reset.html # Reset password form
│   ├── password_reset_done.html
│   ├── password_reset_confirm.html
│   ├── password_reset_complete.html
├── static/                 # Static files (CSS, JS, images)
├── manage.py               # Django management script
├── requirements.txt        # Required Python packages
└── README.md               # Project documentation
```

---

## **Usage**

### **1. Login**
Navigate to `/login/` to access the login form. Provide a valid username/email and password.

### **2. Sign Up**
Visit `/signup/` to create a new account.

### **3. Password Reset**
Go to `/password_reset/` to reset your password:
- Enter your email to receive reset instructions.
- Follow the email link to set a new password.

### **4. Change Password**
Authenticated users can visit `/change_password/` to update their password.

### **5. Dashboard**
Authenticated users are redirected to `/dashboard/` after login.

### **6. Profile**
Visit `/profile/` to view user details.

---

## **Built With**
- **Django**: Python web framework for rapid development.
- **SQLite**: Default database for development.

---

## **Future Improvements**
- Add user email verification during signup.
- Implement a more detailed dashboard with additional features.
- Improve styling and responsiveness.

---

## **Author**
[Shivansh-Ahirwal](https://github.com/Shivansh-Ahirwal)

