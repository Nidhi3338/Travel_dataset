# Travel_Dataset // Data_Engineering project
The travel dataset provides detailed information on various trips taken by travelers, including their destination, travel dates, duration of the trip in days, traveler demographics (name, age, gender, and nationality), as well as the type and cost of accommodation and transportation. This dataset can be used to gain insights into travel patterns, preferences, and behaviors of different types of travelers. It can also be helpful for travel-related businesses, such as travel agencies, to create tailored marketing strategies and travel packages that meet the needs and preferences of different travelers.
### Data source  
- kaggle
- 13 attributes 
1. Trip ID
2. Destination	
3. Start date	
4. End date	
5. Duration (days)	
6. Traveler name	
7. Traveler age	
8. Traveler gender	
9. Traveler nationality	
10. Accommodation type	
11. Accommodation cost	
12. Transportation type	
13. Transportation cost

### column Details
- Trip ID: A unique identifier for each trip taken by a traveler.
- Destination: The name of the city or country visited by the traveler.
- Start date: The date the traveler started the trip.
- End date: The date the traveler ended the trip.
- Duration (days): The number of days the traveler spent on the trip.
- Traveler name: The name of the traveler.
- Traveler age: The age of the traveler at the time of the trip.
- Traveler gender: The gender of the traveler.
- Traveler nationality: The nationality of the traveler.
- Accommodation type: The type of accommodation the traveler stayed in, such as hotel, hostel, or Airbnb.
- Accommodation cost: The cost of the accommodation for the entire trip.
- Transportation type: The mode of transportation used by the traveler, such as plane, train, or car.
- Transportation cost: The cost of transportation for the entire trip.

## BULDING ETL PIPELINE 
  ### Architecture diagram for amazon cloud 
  ![diagram](arch.jpg)
  ## Data Model
  - created 5 tables in Smartdraw website connected each table using Uml diagram
  - this is the class representation 
  ![diagram](model.jpeg)
  ## Cleaning data using pandas 

  - removed null values
  - split the column and got a city string 
  - removed unwanted symbols from the column 
  - removed duplicate data using substring 
  - lastly converted dataframe to csv file  exported into excel 
  
## Relational data 
- find out the cardinality to understand where to assign foriegn key in the entity 
- understanding the normalisation and add columns in the same table because of the analytics performes so duplicates wont be created 
- found of thr age of traveller can be added in diffrent tablr to find where they travel and  at what age, understanding the table and  what we need in the end while querying in the database and what we want to achvie from the data .

	```create database travel;
use traveller;
show tables;
drop table tripinfo;
drop table traveller;
drop table age;
create table tripinfo(trip_id int,destination varchar(15),Start_date date,End_data date,Duration int,Transportation_cost int,Transportation_type varchar(6),Accommodation_type varchar(15),Accommodation_cost int);
create table traveller(traveller_id int,Traveler_name varchar(15),Traveler_gender varchar(20),Traveler_nationality varchar(20));
create table age(traveller_id int,Traveler_age int,trip_id int);
show tables;
alter table traveller  rename to  traveller_data ;
select * from tripinfo;
alter table tripinfo add constraint primary key(trip_id);
select * from traveller_data;
alter table traveller_data  add constraint primary key(traveller_id);

	
