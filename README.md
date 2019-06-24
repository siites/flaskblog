# flaskblog

###### project 생성
```
$ python3 -m venv venv

$ source venv/bin/activate

$ pip install flask

$ pip install flask-wtf

$ pip install flask-sqlalchemy
```

###### db 생성 & 테스트
```
$ python
>>> from app import db
>>> db.create_all()
>>> from app import User, Post
>>> user_1 = User(username='cslee', email='cslee@demo.com', password='password')
>>> db.session.add(user_1)
>>> user_2 = User(username='cslee2', email='cslee2@demo.com', password='password')
>>> db.session.add(user_2)
>>> db.session.commit()
>>> User.query.all()
[User('cslee','cslee@demo.com','default.jpg'), User('cslee2','cslee2@demo.com','default.jpg')]
>>> db.drop_all()
>>> db.create_all()

```

***
###### SECRET_KEY 생성
```
import secrets
secrets.token_hex(16)
```

***
###### Reference
https://youtu.be/QnDWIZuWYW0

https://github.com/CoreyMSchafer/code_snippets/tree/master/Python/Flask_Blog/snippets

https://getbootstrap.com/docs/4.3/getting-started/introduction/