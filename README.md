# Planet API

Welcome to the Planet API repository.

This API allows you to perform CRUD operations on a small seeded database of known planets. You can interact with the API using software like Postman, Insomnia, or any other API testing tool.

![](python_flask_planetary_api_logo.jpg)

## Endpoints

### List all known Planets

```
GET /planets
```

This endpoint retrieves a list of all known planets.

### List Planet details

```
GET /planet_details/<int:planet_id>
```

This endpoint all stored details for a given planet specified in the request by the `planet_id`

### Add new Planets to the database

```
POST /add_planet
```

This endpoint allows authenticated users to add new planets to the database. The request body should include the details of the new planet, including:
- planet_id: Integer (Primary Key)
- planet_name: String
- planet_type: String
- home_star: String
- mass: Float
- radius: Float
- distance: Float

### Update existing planets data

```
PUT /update_planet
```

This endpoint allows authenticated users to update the data of an existing planet. The `planet_id` parameter in the request body specifies the planet to be updated, along with the updated details of the planet.

### Delete planets when necessary

```
DELETE /delete_planet
```

This endpoint allows authenticated users to delete a planet from the database. The `planet_id` parameter in the request body specifies the planet to be deleted.

### Register new users

```
POST /register
```

This endpoint allows users to register by providing the below details in the request body:
- id: Integer (Primary Key)
- first_name: String
- last_name: String
- email: String (Unique)
- password: String

### Authenticate existing users

```
POST /login
```

This endpoint allows existing users to authenticate by providing their username and password in the request body. Upon successful authentication, the API will return a token that should be included in subsequent requests for authentication.

### Retrieving Password
```
GET /retrieve_password/<string:email>
```

This endpoint retrieves the user password through the assigned email.

## Authentication

Authentication is required for certain endpoints. To authenticate, include a token in the Authorization header of the request. The token should be obtained by logging in using the `/login` endpoint.

## Usage

1. To get started, clone this repository and install the required dependencies:

    ```
    git clone https://github.com/romuloParmeggiani/Planetary-api
    cd Planetary-api
    pip install -r requirements.txt
    ```

2. Then, you can run the Flask server:
    
    ```
    python app.py
    ```

3. The server will start running on http://localhost:5000 by default.

### Initializing Database

1. To properly work with the API, first create Database with designed cli command
    ```
    flask db_create
    ```

2. Then seed the Database with the initial demo user and planets data
    ```
    flask db_seed
    ```

3. For test cases, one may also drop the current Database with the given command
    ```
    flask db_drop
    ```

## Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit a pull request with your changes.

## Acknowledgements
Special thanks to the [Bruce Van Horn](https://www.linkedin.com/in/brucevanhorn2/) for very detailed instructions and explanations that allowed to develop this Flask API with so much ease and little code.
