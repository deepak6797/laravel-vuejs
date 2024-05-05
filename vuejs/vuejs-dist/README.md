# To build the application
    - npm run build

# Here dist file have been mounted
    - ./src/dist:/usr/share/nginx/html

# To run the application
    - docker-compose up -d

# To stop the application
    - docker-compose down
