POSTGRES_CONTAINER_NAME=db
WEB_CONTAINER_NAME=web

mkm: ## make migrations
	docker-compose exec ${WEB_CONTAINER_NAME} python manage.py makemigrations

m: ## migrate
	docker-compose exec ${WEB_CONTAINER_NAME} python manage.py migrate

csu: ## create superuser
	docker-compose exec ${WEB_CONTAINER_NAME} python manage.py createsuperuser

bash: ## bash web container
	docker-compose exec ${WEB_CONTAINER_NAME} bash

build: ## build web container
	docker-compose build ${WEB_CONTAINER_NAME}

start: ## start project
	docker-compose up -d

stop: ## stop project
	docker-compose stop

test: ## start tests
	docker-compose exec ${WEB_CONTAINER_NAME} ./manage.py test

h: ## help dialog
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
