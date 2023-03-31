# PyCharm-Fundamentals
Notes on how to code in PyCharm
https://www.jetbrains.com/help/pycharm/creating-and-running-your-first-python-project.html#summary
cd means to add. For example add a folder named mysite: cd mysite
Quit the server with CTRL-BREAK.
Object Oriented programming -> defines what django is as a framework. we can model things and define how they interact w each other
Pep8 > PEP 8, sometimes spelled PEP8 or PEP-8, is a document that provides guidelines and best practices on how to write Python code. According to Pep8,E302 expected 2 blank lines

Polls App


mysite > mysite > polls > models.py

```
class Question(models.Model):
    question_text = models.CharField(max_length=200)
    pub_date = models.DateTimeField('date published')


class Choice(models.Model):
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)
    question = models.ForeignKey(Question, on_delete=models.CASCADE)


```
EXPLANATIONS BELOW

class Question(models.Model): # -> create a new class and call this "Question". Capital M after models.Model to let Django know that the question class is type model
    question_text = models.CharField(max_length=200) # ->  get this class question a question text. All it does is it creates parameter question text, its a CharField
    pub_date = models.DateTimeField('date published')
    
So what we did here is we created two parameters. (11 - 15 lines)
One is a question text one is a pub day and we've said that every question that we create has to have a question text and it has to have a published date.

```
class Choice(models.Model):
    choice_text = models.CharField(max_length=200) -> same as question
    votes = models.IntegerField(default=0)
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
```

And now we need to get the link.There has to be some way where we can say that every choice that we create it links up one and only one question and that's where something called a foreign key comes in.

What the last line does, were giving the choice class a new parameter. And all the parameter says is "were passing in a question".
And this question it has to be a foreign key of this Question object and on delete=cascade -> (Question, on_delete=models.CASCADE)
Whenever we initialize the choice class, whenever we create a new choice it should have a choice text, it's going to have a number of votes 
and it's going to have a question of which it's a one to one relationship.
              
All right there's one last thing we have to do. If you remember when we ran or built in the last video we saw something known as make migrations.
Well we have to do that in this case.
Go to 
```
Terminal > Ctrl + C to end build
```            



django-admin startproject mysite

python manage.py startapp polls

python manage.py runserver

python manage.py makemigrations polls

               
               
               
               
               
               
               
               
               
               
               
               
               
