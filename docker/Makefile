#Makefile
THIS_FILE := $(lastword $(MAKEFILE_LIST))
USER_NAME=st0rik

build_comment:
	export USER_NAME=$(USER_NAME) && cd ../src/comment && bash docker_build.sh
build_ui:
	export USER_NAME=$(USER_NAME) && cd ../src/ui && bash docker_build.sh
build_post-py:
	export USER_NAME=$(USER_NAME) && cd ../src/post-py && bash docker_build.sh
build_prom:
	export USER_NAME=$(USER_NAME) && cd ../monitoring/prometheus && docker build -t $(USER_NAME)/prometheus .
build_blackbox:
	export USER_NAME=$(USER_NAME) && cd ../monitoring/blackbox && docker build -t $(USER_NAME)/blackbox .

build:
	export USER_NAME=$(USER_NAME)
	cd ../src/comment && bash docker_build.sh
	cd ../src/ui && bash docker_build.sh
	cd ../src/post-py && bash docker_build.sh
push:
	docker login
	docker push $(USER_NAME)/ui:logging
	docker push $(USER_NAME)/post:logging
	docker push $(USER_NAME)/comment:logging
	docker push $(USER_NAME)/prometheus:logging
