# Go Pokémon CRUD Application

This is a simple CRUD (Create, Read, Update, Delete) application written in Go for managing Pokémon data. It provides endpoints to perform CRUD operations on a PostgreSQL database containing Pokémon information.

## Team
Sarsembek Arman 21B07051

## Setup

1. **Install Go**: Make sure you have Go installed on your machine. You can download and install it from the [official Go website](https://golang.org/dl/).

2. **Install dependencies**: Run the following commands to install the required dependencies:
    ```bash
    go get -u github.com/gorilla/mux
    go get -u github.com/lib/pq
    ```

3. **Set up PostgreSQL**: Install PostgreSQL and create a database. Update the database connection details in `db/db.go` with your PostgreSQL connection information.

4. **Run the application**: Navigate to the project directory and run the application using the following command:
    ```bash
    go run main.go
    ```

5. **Test the endpoints**: Use tools like cURL, Postman, or a web browser to test the CRUD endpoints. The server runs on port 8080 by default.

## Endpoints

- **POST /pokemon**: Create a new Pokémon. Send a JSON payload with Pokémon details in the request body.
- **GET /pokemon/{id}**: Retrieve a Pokémon by its ID.
- **PUT /pokemon/{id}**: Update an existing Pokémon by its ID. Send a JSON payload with updated Pokémon details in the request body.
- **DELETE /pokemon/{id}**: Delete a Pokémon by its ID.
- **GET /pokemon**: Retrieve all Pokémon from the database.

## JSON Payload Example

```json
{
  "name": "Pikachu",
  "species": "Mouse Pokémon",
  "type1": "Electric",
  "type2": null,
  "height": 0.4,
  "weight": 6.0,
  "base_experience": 112,
  "capture_rate": 190,
  "hp": 35,
  "attack": 55,
  "defense": 40,
  "special_attack": 50,
  "special_defense": 50,
  "speed": 90
}
```

## Database Structure

### Table `pokemon`

| Column Name         | Data Type | Constraints   | Description           |
|---------------------|-----------|---------------|-----------------------|
| id                  | bigserial | primary key   | Unique identifier    |
| name                | text      |               | Name of the Pokémon   |
| species             | text      |               | Species of the Pokémon |
| type1               | text      |               | Primary type of the Pokémon |
| type2               | text      |               | Secondary type of the Pokémon |
| height              | float     |               | Height of the Pokémon |
| weight              | float     |               | Weight of the Pokémon |
| base_experience     | int       |               | Base experience of the Pokémon |
| capture_rate        | int       |               | Capture rate of the Pokémon |
| hp                  | int       |               | Hit points of the Pokémon |
| attack              | int       |               | Attack stat of the Pokémon |
| defense             | int       |               | Defense stat of the Pokémon |
| special_attack      | int       |               | Special attack stat of the Pokémon |
| special_defense     | int       |               | Special defense stat of the Pokémon |
| speed               | int       |               | Speed stat of the Pokémon |
