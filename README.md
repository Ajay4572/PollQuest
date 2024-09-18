
# PollQuest

PollQuest is a full-featured polling app. You have to register in this app to view the polls and vote. If you have already voted, you cannot vote again. Only the owner of a poll can create, edit, update, delete polls, add choices, update choices, delete choices, and end a poll. Once a poll is ended, it can no longer accept votes. Ended polls only show users the final results. There is a search option for polls, and users can filter polls by name, publish date, and number of votes. Pagination works even after applying filters.

## Getting Started

These instructions will help you get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

```text
Python 3.5 or Django 2.0 
```

### Installing

Open your terminal and type:

```bash
git clone https://github.com/Ajay4572/PollQuest.git
```

Or simply download using the URL below:

```text
https://github.com/Ajay4572/PollQuest.git
```

### To Migrate the Database

Open the terminal in the project directory and type:

```bash
python manage.py makemigrations
python manage.py migrate
```

### To Use the Admin Panel

You need to create a superuser using this command:

```bash
python manage.py createsuperuser
```

### To Create Dummy Data

Follow these steps:

```bash
pip install faker
python manage.py shell
import seeder
seeder.seed_all(30)
```

*Here, 30 is the number of entries. You can adjust this as needed.*

## Configure Email

Poll owners receive an email when a vote is cast by a user. Get your SMTP host details and replace the following values in your `settings.py`:

```python
# Configure email settings
EMAIL_HOST = '<your smtp host>'
EMAIL_PORT = '<smtp port>'
EMAIL_HOST_USER = '<smtp host user>'
EMAIL_HOST_PASSWORD = '<smtp host pass>'
DEFAULT_FROM_EMAIL = '<from email address>'
```

### Configuring OAuth Login

<details>
<summary>Obtaining OAuth Client ID for Google</summary>

1. **Go to the Google Cloud Console:**
   - Navigate to [Google Cloud Console](https://console.cloud.google.com/).
   - Sign in with your Google account.

2. **Create a new project:**
   - Click on the project dropdown menu at the top of the page.
   - Click on "New Project" and follow the prompts to create a new project.

3. **Enable the Google Identity service:**
   - Navigate to "APIs & Services" > "Dashboard."
   - Click on "Enable APIs and Services."
   - Search for "Google Identity" and enable it.

4. **Create OAuth consent screen:**
   - Navigate to "APIs & Services" > "OAuth consent screen."
   - Fill in the required fields and save.

5. **Create OAuth credentials:**
   - Navigate to "APIs & Services" > "Credentials."
   - Click on "Create Credentials" > "OAuth client ID."
   - Select "Web application" and add authorized redirect URIs: `http://127.0.0.1:8000/complete/google-oauth2/`.
   - Click "Create."

6. **Copy the client ID and client secret:**
   - Update the following variables in `settings.py`:

   ```python
   SOCIAL_AUTH_GOOGLE_OAUTH2_KEY = 'your-client-id'
   SOCIAL_AUTH_GOOGLE_OAUTH2_SECRET = 'your-client-secret'
   ```

For detailed instructions, refer to Google's documentation on [OAuth 2.0](https://developers.google.com/identity/protocols/oauth2).
</details>

<details>
<summary>Obtaining OAuth Client ID for Facebook</summary>

1. **Create a Facebook App:**
   - Go to [Facebook Developers](https://developers.facebook.com/) and log in.
   - Click on "My Apps" and then "Create App".
   - Fill in the required information.

2. **Configure Basic Settings:**
   - Go to Settings > Basic.
   - Add a platform (select Website) and enter your site URL: `http://127.0.0.1:8000/complete/facebook/`.
   - Save your changes.

3. **Get App ID and App Secret:**
   - Update the following settings in your `settings.py`:

   ```python
   SOCIAL_AUTH_FACEBOOK_OAUTH2_KEY = 'your-client-id'
   SOCIAL_AUTH_FACEBOOK_OAUTH2_SECRET = 'your-client-secret'
   ```
</details>

<details>
<summary>Obtaining OAuth Client ID for LinkedIn</summary>

1. **Create a LinkedIn App:**
   - Go to the [LinkedIn Developer Portal](https://www.linkedin.com/developers/) and sign in.
   - Click on "Create App" and fill in the required details.
   - Add the callback URL for your Django app: `http://127.0.0.1:8000/complete/linkedin/`.

2. **Configure Django Settings:**
   - Update the following settings in `settings.py`:

   ```python
   SOCIAL_AUTH_LINKEDIN_OAUTH2_KEY = 'your-client-id'
   SOCIAL_AUTH_LINKEDIN_OAUTH2_SECRET = 'your-client-secret'
   ```
</details>

### To Run the Program on Local Server

Use the following command:

```bash
python manage.py runserver
```

Then go to [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

## Project Snapshot

### Home Page
![Home Page](https://user-images.githubusercontent.com/19981097/51409444-0e40a600-1b8c-11e9-9ab0-27d759db8973.jpg)

### Login Page
![Login Page](https://user-images.githubusercontent.com/19981097/51409509-36c8a000-1b8c-11e9-845a-65b49262aa53.png)

### Registration Page
![Registration Page](https://user-images.githubusercontent.com/19981097/51409562-5cee4000-1b8c-11e9-82f6-1aa2df159528.png)

### Poll List Page
![Poll List Page](https://user-images.githubusercontent.com/19981097/51409728-d423d400-1b8c-11e9-8903-4c08ba64512e.png)

### Poll Add Page
![Poll Add Page](https://user-images.githubusercontent.com/19981097/51409796-fe759180-1b8c-11e9-941b-c1202956cca4.png)

### Polling Page
![Polling Page](https://user-images.githubusercontent.com/19981097/51409843-1e0cba00-1b8d-11e9-9109-cceb79a6a623.png)

### Poll Result Page
![Poll Result Page](https://user-images.githubusercontent.com/19981097/51409932-60ce9200-1b8d-11e9-9c83-c59ba498ca8b.png)

### Poll Edit Page
![Poll Edit Page](https://user-images.githubusercontent.com/19981097/51410008-92dff400-1b8d-11e9-8172-c228e4b60e28.png)

### Choice Update/Delete Page
![Choice Update/Delete Page](https://user-images.githubusercontent.com/19981097/51410442-dc7d0e80-1b8e-11e9-8f8e-18e6d7bb70fb.png)

### Dashboard Page
![Dashboard Page](https://github.com/devmahmud/Django-Poll-App/assets/17628879/46bd5f4d-b236-44c4-8636-2e171e2173e5)

## Author
**Ajay Kumar**  
Email: ajaysnb64@gmail.com

<div align="center">
    <h3>========Thank You !!!=========</h3>
</div>
```

Feel free to adjust any sections further if needed!
