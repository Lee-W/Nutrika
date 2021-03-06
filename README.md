# Nutrika
## Description
a restful website visualizing Taiwan FDA food nutrition fact of items you select

## What we use
1. Frontend:
  * React: app architecture
  * Redux: state container
  * Redux-Thunk
  * Redux-Saga
  * d3, [recharts](https://github.com/recharts/recharts): visualize the data
1. Backend:
  * Django, Django REST framework: backend api
  * Python: crawler

## Feature
1. select(pin) the items and see their nutrition facts
1. fill the target-form(calories, fat, protein and carbs) and get the comparison between target and select items

## Others
We use redux-thunk and redux-saga to implement redux async actions. To avoiding over-frequently request to server, we use redux-saga to set timeout when you type the search keyword.

## Setup
1. Install [postgresql](https://www.postgresql.org/download/)

2. [Optional] Create virtual envirnment
3. 
	```sh
	virtualenv --no-site-package venv
	```

3. Install dependency  
	
	```sh
	pip install -r requirements.txt
	```

4. Create user nutrika  
	
	```sh
	createuser -Psrle nutrika
	```

	If you get the error `psql: could not connect to server`, 	read the [this post](
http://dba.stackexchange.com/questions/75214/psql-could-not-connect-to-server-no-such-file-or-directory)

5. Create db nutrika    

	```sh
	createdb nutrika
	```

6. Insert Data into Database

	```sh
	python manage.py import_nutrition
	```

7. Run server

	```sh
	python manage.py runserver
	```


## Todos
1. form to add items
1. algorithm to filter unreliable information
1. add items by photo(maybe...)
