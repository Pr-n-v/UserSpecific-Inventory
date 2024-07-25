# User Specific Inventory Management System

## Overview

This project is a blockchain-based inventory management system implemented in Go. It allows users to register, log in, and manage their inventories by adding and removing items. The changes in inventory are recorded on the blockchain, ensuring integrity and traceability. The system also supports real-time inventory updates and transaction logging.

## Features

- **User Authentication**: Users can sign up and log in using a secure authentication mechanism.
- **Blockchain Implementation**: Each inventory transaction is recorded on the blockchain.
- **Inventory Management**: Users can add or remove items from their inventory.
- **Transaction History**: Users can view their inventory transaction history.
- **Blockchain Audit**: The blockchain can be audited for integrity.
- **Real-Time Updates**: Real-time updates of inventory changes for each user.

## Dependencies

- Go (Golang)
- `golang.org/x/crypto/bcrypt` for password hashing

## Setup

1. **Install Go**: Make sure Go is installed on your machine. You can download it from [here](https://golang.org/dl/).

2. **Set Up Your Project**:

    Create a new directory for your project:
    ```sh
    mkdir myproject
    cd myproject
    ```
    Initialize a new Go module (if you haven't already):
    ```sh
    go mod init myproject
    ```
    Fetch the bcrypt Package:
    
    ```sh
    go get golang.org/x/crypto/bcrypt
    ```
    
    More information for `bcrypt` at: [golang.org/x/crypto/bcrypt](https://pkg.go.dev/golang.org/x/crypto/bcrypt).


3. **Clone the Repository**: Clone this repository to your local machine.

```sh
git clone https://github.com/yourusername/blockchain-inventory.git
cd blockchain-inventory
```

4. **Run the Program**: Run the main Go program.

```sh
go run main.go
```

## Usage

### Authentication

1. **Sign Up**:
    - Choose the "Signup" option from the menu.
    - Enter a username and password for registration.

2. **Log In**:
    - Choose the "Login" option from the menu.
    - Enter your username and password to log in.

### Main Menu

After logging in, the main menu provides the following options:

1. **Add item to inventory**:
    - Enter the item name and quantity to add to the inventory.

2. **Remove item from inventory**:
    - Enter the item ID and quantity to remove from the inventory.

3. **View inventory**:
    - Displays the current inventory for the logged-in user.

4. **Audit blockchain**:
    - Audits the blockchain for integrity and correctness.

5. **View transaction history**:
    - Displays the transaction history for the logged-in user.

6. **View Blockchain**:
    - Displays the latest block and its inventory transactions in the blockchain.

7. **Logout**:
    - Logs out the current user and returns to the login/signup menu.

## File Structure

- `main.go`: The main Go file containing the entire implementation.
- `user_list.json`: Stores user credentials.
- `blockchain.json`: Stores the blockchain data.
- `{username}_transactions.json`: Stores transaction history for each user.

## Functions

### Authentication Functions

- `Initialize() error`: Initializes the authentication system.
- `RegUser(username, password string) error`: Registers a new user.
- `Authentication(username, password string) bool`: Authenticates a user.

### Blockchain Functions

- `calculateHash(b Block) string`: Calculates the hash for a block.
- `createGenesisBlock(difficulty int) Block`: Creates the genesis block.
- `createNewBlock(previousBlock Block, data string, difficulty int, inventoryTransactions []InventoryItem) Block`: Creates a new block.
- `Initialize()`: Initializes the blockchain and user inventories.

### Inventory Management Functions

- `addInventoryItem(blockchain *Blockchain, username, name string, quantity int)`: Adds an item to the inventory.
- `removeInventoryItem(blockchain *Blockchain, username string, id, quantity int)`: Removes an item from the inventory.
- `viewInventory(blockchain *Blockchain, username string)`: Views the inventory for a user.
- `viewBlockchain(blockchain *Blockchain, username string)`: Views the blockchain for a user.
- `auditBlockchain(blockchain *Blockchain)`: Audits the blockchain.
- `logTransactions(blockchain *Blockchain, username string)`: Logs transactions for a user.

### Utility Functions

- `saveBlockchain(blockchain *Blockchain)`: Saves the blockchain to a file.
- `loadBlockchain() Blockchain`: Loads the blockchain from a file.
- `updateListener(blockchain *Blockchain, username, itemName string)`: Updates inventory in real-time.
- `loadUserTransactions(username string) []Transaction`: Loads user transactions from a file.
- `saveUserTransactions(username string, transactions []Transaction)`: Saves user transactions to a file.

## Notes

- Ensure that you have proper permissions to read/write files in the directory where the program is executed.
- The system uses bcrypt for password hashing, providing a secure method for storing user passwords.
- The blockchain ensures the integrity and traceability of all inventory transactions.

##Contributions made by : 
Rohan Anantapur : https://github.com/rohan-0201 
Sripriya Addanki : https://github.com/sripriya204

