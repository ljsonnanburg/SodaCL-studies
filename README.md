# SodaCL-studies
Look at me I'm learning SodaCL

So far this only includes the adventureworks PostgreSQL data Soda uses for their tutorial. Commented checks are in the adventureworks folder.
![dashboard1](https://github.com/ljsonnanburg/SodaCL-studies/assets/81723569/889a5e7d-34ec-402f-b1f8-1078079aeafc)
This image shows that of all the databases I ran checks on, only fact_reseller_sales completed without any failures.
![dashboard_dim_customer](https://github.com/ljsonnanburg/SodaCL-studies/assets/81723569/7168bdd7-8602-436f-b777-67d2103d8ad5)
This image shows which checks passed and failed for the dataset dim_customer. 
The first check failed because the data is too old, and the VALUE column displays how old the most recent data entry is.
The second check failed because there are 715 duplicate phone numbers.
The remaining checks passes: there are no null last name values, the schema hasn't changed, and all email addresses are valid.
![dashboard_dim_product](https://github.com/ljsonnanburg/SodaCL-studies/assets/81723569/4a0e0f68-9876-43dc-8091-b873bbc6eae2)
The checks for dim_product failed because 36.30% of products ordered showed up as having illegal colors and it has a different number of rows from dim_product_category.
![dashboard_fact_product_inventory](https://github.com/ljsonnanburg/SodaCL-studies/assets/81723569/b970985a-b244-47f3-a541-17676666a18c)
The check for fact_product_inventory failed because 494 items showed up as having a negative item balance, which I believe means they're trying to sell more product than they have?
There was no data dictionary.
I was attempting to set up a warning for when unit_balance dips below a threshold indicating a need to order more of the item, but that threshold comes from another dataset and as far as I can tell there's no way to join them within SodaCL, and that threshold would need to be included i nthe schema for fact_product_inventory. Still investigating this.
![dashboard_fact_reseller_sales](https://github.com/ljsonnanburg/SodaCL-studies/assets/81723569/18b0f8d5-5f6f-47ed-93df-25b8042b78d5)
The check for fact_reseller_sales passed because less than 5% of all orders shipped after their due date.
