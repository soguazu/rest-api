# rest-api
Simple REST API application implemented with Node.js, GraphQL, Postgres

### Getting Started
*********
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 
### Prerequisites


Install Node.js [here](https://nodejs.org/en/)


 Install Postgres Mac
 1. Make sure you brew installed
 2. brew install postgres
 3. after installation - create a user to be able to create database. type this in your terminal $ psql postgres
 4. CREATE ROLE your_user_name_of_your_choice WITH LOGIN PASSWORD 'your_password_of_your_choice';
 5. ALTER ROLE your_user_name_of_your_choice CREATEDB;
 6. Logout by typing this in your terminal -  $exit
 7. and login with your new created username - $psql postgres -U your_user_name_of_your_choice;
 8. CREATE DATABASE league  //to create a database
 9. \connect league
 10. Copy the code below to create tables
 
 
 ```
 CREATE TABLE team (
  id SERIAL PRIMARY KEY,
  name VARCHAR (255)
);
CREATE TABLE player (
 id SERIAL PRIMARY KEY,
 first_name VARCHAR (255),
 last_name VARCHAR (255),
 team_id INT NOT NULL REFERENCES team (id)
);
CREATE TABLE match (
  id SERIAL PRIMARY KEY,
  date DATE NOT NULL DEFAULT CURRENT_DATE,
  winner_team_id INT NOT NULL REFERENCES team (id),
  loser_team_id INT NOT NULL REFERENCES team (id)
);
```


### Installing


```
git clone https://github.com/soguazu/rest-api.git
```

```
cd rest-api
```

```
npm install
```

## Authors

* **Stanley Oguazu** - *Initial work* - [soguazu](https://github.com/soguazu)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details


