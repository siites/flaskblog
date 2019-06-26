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
###### bcrypt
```
>>> from flask_bcrypt import Bcrypt
>>> bcrypt = Bcrypt()
>>> bcrypt.generate_password_hash('testing')
b'$2b$12$t8ocJPJ7YbHdWUoxMKNoxetn50kPthF96te/yagKZA5JStoYtEa86'
>>> bcrypt.generate_password_hash('testing').decode('utf-8')
'$2b$12$3h2C3XacveITxvg6WvL4ee/QHp9ejTn/gOUWEZ7.MBsRVawLx4D2K'
>>> bcrypt.generate_password_hash('testing').decode('utf-8')
'$2b$12$qzsMp21u.FsUUoO8/beuMOUgzTBpT5ItUXTUzBEtPIQNvbI2DRR7K'
>>> bcrypt.generate_password_hash('testing').decode('utf-8')
'$2b$12$GtUotcjBEbdGYpN0BqFSzeExRngy34LAZgCwEH287wa0pXd4.Pn/C'
>>> hashed_pw = bcrypt.generate_password_hash('testing').decode('utf-8')
>>> bcrypt.check_password_hash(hashed_pw, 'password')
False
>>> bcrypt.check_password_hash(hashed_pw, 'testing')
True
>>> exit()
```
***
###### Reference
https://youtu.be/QnDWIZuWYW0

https://github.com/CoreyMSchafer/code_snippets/tree/master/Python/Flask_Blog/snippets

https://getbootstrap.com/docs/4.3/getting-started/introduction/