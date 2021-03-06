# Relationship Manager

### Synopsis

![gif](https://cloud.githubusercontent.com/assets/19376513/20638960/26102ab6-b36b-11e6-9b5c-939a75d1025a.gif)

Relationship Manager helps users nurture the most important relationships in their lives. Have you ever been in a situation where you lost touch with a friend after you transitioned to a new job or to a new city? What about with former coworkers or bosses? Are you as close with them as you would like? Some relationships are too important or too valuable for us to afford losing, yet, many of us do not actively set aside time to remind ourselves to reach out to that person.

Similarly, when was the last time that you were at a networking event or a company party where you couldn't remember a particular fact about someone or didn't have anything to talk about with that important someone? It's good practice to keep track of the likes, dislikes, goals, preferences, etc. about every meaningful person, and that's best accomplished when documented immediately. That's where my app comes in handy. Record observations and imagine how much more impactful your follow-ups would be if you could accurately recall the details shared in your last interaction with that person. 
 
### Adding Contacts

![alt text](https://cloud.githubusercontent.com/assets/19376513/20638976/bbb9f7fe-b36b-11e6-9e73-2b96b29c3ab0.png)

To get started, users add their closest circle, then categorize each contact by 'Friend,' 'Family' or 'Professional' and events are scheduled with a tip on how to reach out.

![alt text](https://cloud.githubusercontent.com/assets/19376513/20638996/61e0527c-b36c-11e6-8e8f-9e445d7d1c80.png)

Users have the option of signing up using their Facebook account. The JavaScript SDK was used for the OAuth.

![alt text](https://cloud.githubusercontent.com/assets/19376513/20639061/cce572b8-b36d-11e6-99cf-bab0738e60a0.png)

### Receive Notifications
 
Emails are sent to the user using Python's SMTP library. Depending on the type of contact, the scheduled frequency of tips and events will vary - quarterly for professional contacts and monthly for friends and family. The Schedule API acts as a cron job, querying the database hourly to see which events had most recently elapsed, and sending emails for those events. A notification for a mentor (professional contact), for example, would look like: "Rachel, it's been three months since your last meeting with your mentor, Jane Doe. Send her a quick email to see how she's doing! She would love to hear from you." Reminders about a contact who is a friend would suggest: "Hey Rachel! Jessica has been wondering about you. Take time to grab dinner with her this week."

### Store Info about Contacts

![alt text](https://cloud.githubusercontent.com/assets/19376513/20639008/a17fa2de-b36c-11e6-8f01-9b4bc71eacbc.png)

Users can store information about their contact's favorite drink, sports team, gift ideas, goals, pets, family information, etc. JSON is used to store the information in the database and AJAX is used to asynchronously render inputted text on the browser immediately.

### Database

The relational PostgreSQL database was used to store information and SQLAlchemy was used for the queries. Object-oriented programming was used to structure the schema of the model. A view inclusive of all upcoming events with all contacts has been included as well:

![upcoming-events](https://cloud.githubusercontent.com/assets/19376513/20639105/39371830-b36f-11e6-8270-cab6c57f5495.gif)


### Installation Instructions

Step 1: Create a copy of the project on your local machine.

```python
git clone https://github.com/yfalcon8/relationship_manager_project
```

Step 2: Create and name a virtual environment.

```python
virtualenv env
```

Step 3: Download necessary programs, libraries and packages.

```python
pip install -r requirements.txt
```

Step 4: On line 134 in sendnotif.py, type your email address and email password in place of YOUR_EMAIL_ADDRESS and YOUR_EMAIL_PASSWORD, respectively. For obvious security reasons, I excluded my own information.

Step 5: Fire up the server!

```python
python server.py
```

### Tech Stack
- Python
- JavaScript
- jQuery
- Object-oriented programming
- PostgreSQL
- SQL
- SQLAlchemy
- JSON
- AJAX
- Flask
- Jinja
- HTML
- CSS
- Bootstrap
- Arrow library (datetime)
- SMTP library (email)

### APIs
- Facebook OAuth API
- Schedule API

### Building the App

Check out my [blog](http://yfalcon8.wixsite.com/yuki-falcon) for more about my journey in creating this app!

### Heroku

Check out the deployed version on [Heroku](https://yf-relationship-manager.herokuapp.com/)!
