## Veve Assests Data Scraper:
 - VeVe is a marketplace for premium licensed digital collectibles. With VeVe, users can obtain limited edition or one-of-a-kind digital collectibles, showcase them in virtual showrooms as well as buy, sell or trade collectibles with other VeVe users.
- We are going to scrap assests data from the veve including,

    - Name
    - Store Price
    - Rarity
    - EditionType
    - Total Assests, 
    - Avaiable Assests,
    - Licence
    - Brand
    - etc.


![veve](https://github.com/HammadRafique29/veve-scraper/assets/112252001/67e32335-14f2-4c25-b92a-5b6257716578)

 ![4](https://github.com/HammadRafique29/veve-scraper/assets/112252001/b4a51fc8-948c-4d40-b138-1861a056614f)


https://github.com/HammadRafique29/veve-scraper/assets/112252001/2abfe027-04ed-459a-b633-b8d7aa89792a


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

## Contact Me For Script:

- **Skype:** [live:.cid.85ec2e63e4558292](skype:your_skype_id?chat) :calling:
- **Upwork:** [M Hammad Rafique](https://upwork.com/freelancers/hammadr33) 
- **Gmail:** [Python Developer 029](pythondeveloper029@gmail.com)  | [Coding Magician](codingmagician0@gmail.com)  :email:

---

Thank you for exploring my profile. If you have any questions or would like to discuss a project, feel free to reach out to me. I look forward to the possibility of working together!

Best regards,  
[Hammad Rafique](https://github.com/HammadRafique29)

[LinkedIn](https://www.linkedin.com/in/hammad-rafique-hr029) | [GitHub](https://github.com/HammadRafique29) | [Instagram](https://www.instagram.com/hammad_rafique1449/?utm_source=qr&r=nametag)

