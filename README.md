# Restaurant GraphQL API

This is a simple GraphQL API that allows you to perform CRUD (Create, Read, Update, Delete) operations on a list of restaurants.

## Requirements

Node.js installed on your machine.

## Installation

1. Clone this repository:
    ```
    git clone <repository-url>
    ```
2. Install dependencies:
    ```
    npm install
    ```
    
## Running the server

To run the server, use the following command:

    node index.js


The server should now be running at `http://localhost:5500/graphql`.

## Using the API

You can interact with the API using a GraphQL client like GraphiQL. The following operations are supported:

- `restaurant({id: Int})`: Fetch a single restaurant by its ID.
- `restaurants`: Fetch all restaurants.
- `setrestaurant({input: {name: String, description: String}})`: Create a new restaurant.
- `deleterestaurant({id: Int})`: Delete a restaurant by its ID.
- `editrestaurant({id: Int, name: String, description: String})`: Update a restaurant by its ID.

## Example queries

1. Fetch a single restaurant:
    ```graphql
    query {
      restaurant(id: 1) {
        id
        name
        description
      }
    }
    ```

2. Fetch all restaurants:
    ```graphql
    query {
      restaurants {
        id
        name
        description
      }
    }
    ```

3. Create a new restaurant:
    ```graphql
    mutation {
      setrestaurant(input: {name: "New Restaurant", description: "New Description"}) {
        id
        name
        description
      }
    }
    ```

4. Delete a restaurant:
    ```graphql
    mutation {
      deleterestaurant(id: 1) {
        ok
      }
    }
    ```

5. Update a restaurant:
    ```graphql
    mutation {
      editrestaurant(id: 2, name: "Updated Name", description: "Updated Description") {
        id
        name
        description
      }
    }
    ```

Please note that the above queries are examples and actual usage will depend on the data you have in your application.
