## libraries that you need to install

pip install flask-sqlalchemy
pip install flask
pip install flask-wtf
pip install email_validator
pip install flask_bcrypt
pip install flask_login


## How to run flask project

### 1st method:

set FLASK_APP=nameofthefile.py
set FLASK_DEBUG=1
flask run

### 2nd method:

1.write next line in main.py file:
if __name__ == '__main__':     
    app.run(debug=True)

2. use this command in terminal
python main.py  		    




## using sqlite as db and terminal commands

first we should write class Table
after that execute command below

### to create Table:
- python
- from market import app, db
- app.app_context().push()
- db.create_all()

### To add data to table:
- from market.models import Item
- item1 = Item(name="IPhone 10", price=500, barcode='846154104831', description='desc')
- db.session.add(item1)
- db.session.commit()

### To check table data:
- Item.query.all()

### To exit:
- exit()


### to work with item1:
- item1 = Item.query.filter_by(name='Iphone 10').first()
- item1.owner = User.query.filter_by(username='jc').first().id  
- db.session.add(item1)
- db.session.commit()                                        
- item1.owner

### To rollback to prev changes:
- db.session.rollback()


