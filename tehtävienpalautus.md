# Viikko 2 / Yhteen tauluun kohdistuvat kyselyt ja where-osan liitosehto

select * from goal;

![image](https://github.com/user-attachments/assets/4b0d2ae1-8fd7-4abd-b18c-b27c359c725a)


select name from airport where iso_country = "FI";

![image](https://github.com/user-attachments/assets/1de33a3d-f264-4f00-aaac-5d4cfb209429)
![image](https://github.com/user-attachments/assets/a7096ae9-c56b-4ecb-978c-0739ad8935a6)



select name from airport where iso_country = "FI" order by name;

![image](https://github.com/user-attachments/assets/8aaec425-a7b4-47f4-9d05-402ab7cfe7ff)
![image](https://github.com/user-attachments/assets/1e3bc076-5c95-4c19-a012-8ee29402d1d6)


select name, type from airport where iso_country = "FI" order by type, name;

![image](https://github.com/user-attachments/assets/ac83fd42-8ee3-40ba-93c0-2c63796a6756)
![image](https://github.com/user-attachments/assets/a4c24286-753c-4010-90b1-56aa34b76d27)



select name from country where name like "F%";

![image](https://github.com/user-attachments/assets/3849438c-c8d6-43f0-9bb8-133d5ecabb14)


select name from country where name like "%F%";

![image](https://github.com/user-attachments/assets/ba4db837-5dba-4826-a261-38d1dede6467)


select location from game where screen_name = "Vesa";

![image](https://github.com/user-attachments/assets/e2d2f633-c30e-40b6-8b29-878761a08b25)


select co2_consumed from game where screen_name = "Ilkka";

![image](https://github.com/user-attachments/assets/801e8432-a346-4bc4-8518-ee2b4eae10d9)


select co2_budget from game limit 1;

![image](https://github.com/user-attachments/assets/198e23b6-c016-4c8a-ba93-111f0e713157)


