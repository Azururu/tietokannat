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


select country.name as "country name", airport.name as "airport name"
from airport, country
where airport.iso_country = country.iso_country and country.name = "Iceland";

![image](https://github.com/user-attachments/assets/5794b060-f355-4833-8763-2eec92bf371f)
![image](https://github.com/user-attachments/assets/dce64b74-8ca3-4112-ad14-933e66efba5f)


select airport.name as "airport name"
from airport, country
where airport.iso_country = country.iso_country and country.name = "France" and airport.type = "large_airport";

![image](https://github.com/user-attachments/assets/222dda40-d5a7-466b-9fcb-de69e6822c53)


select country.name as "country_name", airport.name as "airport_name"
from country, airport
where airport.iso_country = country.iso_country and country.continent = "AN";

![image](https://github.com/user-attachments/assets/f0949c63-5439-42b6-b9d2-6f6ddcdab797)
![image](https://github.com/user-attachments/assets/33b5887f-a9b3-4a5d-bfbc-f57a84eaa91b)


select airport.elevation_ft
from airport, game
where airport.ident = game.location and game.screen_name = "Heini";

![image](https://github.com/user-attachments/assets/40a1583c-78dc-4768-a480-ac0b06d1ba07)


select airport.elevation_ft * 0.3048 as "elevation_m"
from airport, ggame
where airport.ident = game.location and game.screen_name = "Heini";

![image](https://github.com/user-attachments/assets/e0b1374d-30d1-46e5-a562-c1400db40879)


select airport.name
from airport, game
where airport.ident = game.location and gamme.screen_name = "Ilkka";

![image](https://github.com/user-attachments/assets/eb785839-cbc3-4de1-9259-110c25950382)


select country.name
from country, airport, game
where airport.ident = game.location and country.iso_country = airport.iso_country and game.screen_name = "Ilkka";

![image](https://github.com/user-attachments/assets/179503b1-4470-4b71-8375-62bfa9237a1a)


select name
from goal, goal_reached, game
where game.id = game_id and goal.id = goal_id and screen_name = "Heini";

![image](https://github.com/user-attachments/assets/9f0d1335-86c4-4a93-8e95-5705989de31d)


select airport.name
from airport, goal, goal_reached, game
where game.id = game_id and goal.id = goal_id and game.location = airport.ident
and goal.name = "CLOUDS" and screen_name = "Ilkka";

![image](https://github.com/user-attachments/assets/e709f05d-0856-4610-8d7c-d079deb2bcee)


select country.name
from goal, goal_reached, game, airport, country
where airport.iso_country = country.iso_country and airport.ident = game.location
and game.id = game_id and goal.id = goal_id
and screen_name = "Ilkka" and goal.name = "CLOUDS";

![image](https://github.com/user-attachments/assets/434e69f1-048c-4511-8d62-bcd0742deb5d)
