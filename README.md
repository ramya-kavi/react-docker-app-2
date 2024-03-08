


docker build -t react-app-2 .

docker build -f Dockerfile.dev -t react-app-2 .


docker run -p 3000:3000 react-app-2

docker image rm imageid


docker exec -it react-app-2 bash

bind local to app
# powershell
docker run -e WATCHPACK_POLLING=true -v ${pwd}\src:/app/src -d -p 3000:3000 react-app-2 

# powershell read only
docker run -e WATCHPACK_POLLING=true -v ${pwd}\src:/app/src:ro -d -p 3000:3000 react-app-2 

# cmd
docker run -v %cd%\src:/app/src -d -p 3000:3000 react-app-2 

# powershell with .env
docker run --env-file ./.env -v ${pwd}\src:/app/src -d -p 3000:3000 react-app-2       


compose file

docker-compose up -d --build
docker-compose up -d

docker-compose down

docker-compose -f docker-compose.yml -f docker-compose-dev.yml up -d --build


