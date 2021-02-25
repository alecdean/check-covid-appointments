# MA Vaccine Appointment Checker

## Description

This is a simple Python program that checks the Massachusetts' COVID vaccine appointment website every so often for availablities.

## Installation

This program requires the following dependencies:

- Python 3
  - To install, go to [Python's website](https://www.python.org/downloads/) and download the most recent version of Python
  - During the install process, make sure *Add Python 3.x to PATH* is checked
  - you should be able to open a command line and run ```python --version```
- Packages
  - Please install the following python packages by running the following commands:
  
  ```
  pip install beautifulsoup4
  pip install requests
  ```

- Beautiful Soup 4: This library makes it easier to parse the html from web pages
- Requests: This is a library to make http requests to the vaccine appointment website
- Git
  - Check to see if Git is already installed by running ```git --version```
  - If it's not installed, head to [Git's website](https://git-scm.com/download/win) to install

In addition to those dependencies, you need to edit the config file **config.json** to include your corresponding information, such as email addresss and Google App credentials.

### Google App Setup

By setting up Gmail App credentials, you are allowing this program to send you mail, notifying you when an appointment becomes available.

To create your gmail app credentials, follow these steps:

1. Go to your Google Account settings at [My Google Account](https://myaccount.google.com/)
2. On the left sidebar, select **Security**
3. Under the *Signing in to Google Section*, select **App Passwords**
4. Enter your Google Password if necessary
5. Click **Select App**, and select **Mail**
6. Click **Select Device**, and choose the corresponding device
7. Click **Generate**
8. Copy and paste the generated password into *config.json*

**Note**: Google creates these passwords for you as an added layer of security, so that you don't have to type in your own Google password.

## Usage

Copy the program to your computer by running 
```
git clone https://github.com/alecdean/check-covid-appointments.git
cd check-covid-appointments
```

### Configuration

Please fill out the config.json file to your preferences:

```
{
    // email information
    "your_email":"",

    // your username (without the @gmail.com part)
    "your_gmail_username": "",

    // please follow the instructions on the README to get your google app password
    "your_google_app_password":"",

    // set to true if you'd like to see the average number of requests per minute
    "print_statistics": false,

    // set to true if you'd an email notification of an appointment
    "send_email_notification": false,

    // set to false if you don't want a beep to notify you of an opening
    "play_sound": true,

    // set to true if you'd like to search on 03/03/2021 specifically
    "specific_date": true,
    
    // IMPORTANT: adjust this number to the expected number of pages that you can click through
    // each additional page takes an extra few seconds to search, so the more pages there are, the longer the program will take
    "num_pages":1
}

```

### Running

Once you've filled out the *config.json* file to your satisfaction, simply run the following commands:

```
python vaccines.py
``` 

After running the last command, you should begin to see the results of each search printed every few seconds.
