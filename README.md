## Veve Assests Data Scraper:
 - VeVe is a marketplace for premium licensed digital collectibles. With VeVe, users can obtain limited edition or one-of-a-kind digital collectibles, showcase them in virtual showrooms as well as buy, sell or trade collectibles with other VeVe users.
- We are going to scrap assests data from the veve including,

    - Name
    - Store Price
    - Rarity
    - EditionType
    - Total Assests, 
    - Avaiable Assests, 
    - etc.

## INSTALLATION:
 - `pip install -r requirements.txt`
 - Add your `veve` token in `cookies.json`. (From API Request using Browser Console)

## RUNNING:
 - `py veve_scrap.py`

## STORING DATA IN SQL SERVER:

Based on your Python code, here are the steps to set up your database and table in SQL Server:

1. **Connect to SQL Server**: Make sure you have installed SQL Server and SSMS. Open SSMS and connect to your SQL Server instance.

2. **Create a Database**: Right-click on "Databases" in Object Explorer, select "New Database..." and name it `Vevescrape` (or any other desired name).

3. **Create Tables**:
   - Right-click on your database (`Vevescrape`) in Object Explorer, select "New Query".
   - Use the following SQL statements to create the necessary tables:

     ```sql
     CREATE TABLE series (
         id INT PRIMARY KEY IDENTITY(1,1),
         series_id VARCHAR(255) NOT NULL,
         series_name VARCHAR(255) NOT NULL,
         series_url VARCHAR(255) NOT NULL
     );

     CREATE TABLE licensor (
         id INT PRIMARY KEY IDENTITY(1,1),
         licensor_id VARCHAR(255) NOT NULL,
         licensor_name VARCHAR(255) NOT NULL,
         licensor_url VARCHAR(255) NOT NULL
     );

     CREATE TABLE brand (
         id INT PRIMARY KEY IDENTITY(1,1),
         brand_id VARCHAR(255) NOT NULL,
         brand_name VARCHAR(255) NOT NULL,
         brand_url VARCHAR(255) NOT NULL
     );

     CREATE TABLE collectible (
         id INT PRIMARY KEY IDENTITY(1,1),
         collectible_id VARCHAR(255) NOT NULL,
         url VARCHAR(255) NOT NULL,
         name VARCHAR(255) NOT NULL,
         drop_date DATE NOT NULL,
         total_available INT NOT NULL,
         total_issued INT NOT NULL,
         edition_type VARCHAR(255) NOT NULL,
         rarity VARCHAR(255) NOT NULL,
         store_price DECIMAL(10, 2) NOT NULL,
         licensor_id INT NOT NULL,
         brand_id INT NOT NULL,
         series_id INT NOT NULL,
         series_season INT NOT NULL,
         FOREIGN KEY (licensor_id) REFERENCES licensor(id),
         FOREIGN KEY (brand_id) REFERENCES brand(id),
         FOREIGN KEY (series_id) REFERENCES series(id)
     );

     CREATE TABLE seller (
         id INT PRIMARY KEY IDENTITY(1,1),
         seller_id VARCHAR(255) NOT NULL,
         seller_name VARCHAR(255) NOT NULL
     );

     CREATE TABLE collectiblelisting (
         id INT PRIMARY KEY IDENTITY(1,1),
         collectible_id INT NOT NULL,
         token VARCHAR(255) NOT NULL,
         seller_id INT NOT NULL,
         issue_number VARCHAR(255) NOT NULL,
         price DECIMAL(10, 2) NOT NULL,
         FOREIGN KEY (collectible_id) REFERENCES collectible(id),
         FOREIGN KEY (seller_id) REFERENCES seller(id)
     );
     ```

4. **Execute the Python Code**: With the database and tables created, you can now execute your Python code. It will insert data into the tables as specified in the code.

Please make sure to replace the placeholders in the SQL statements (`VARCHAR(255)`, `DECIMAL(10, 2)`, etc.) with appropriate data types and lengths based on your requirements.