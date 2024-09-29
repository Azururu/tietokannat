# Viikko 1
Palautettu moodlessa

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


# Viikko 3 / Join ja sisäkyselyt

select country.name as "country name", airport.name as "airport name"
from country
inner join airport on airport.iso_country = country.iso_country
where country.name = "Finland" and scheduled service = "yes";

![image](https://github.com/user-attachments/assets/336565ff-b8dd-449e-ab45-8bcf3e65c1cb)


select game.screen_name, airport.name
from game
inner join airport on airport.ident = game.location;

![image](https://github.com/user-attachments/assets/1a43a139-29f9-42f1-8d9b-b8c919e2ed6d)


select game.screen_name, country.name
from game
inner join airport on game.location = airport.ident
inner join country on airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/c44e355f-a972-4d6e-bac9-fe25a4263cae)


select airport.name, game.screen_name
from airport
left join game on airport.ident = game.location
where name like "%Hels%";

![image](https://github.com/user-attachments/assets/d3b9e11a-aab2-4cba-aecc-ad4bb53f3663)


select goal.name, game.screen_name
from goal
left join goal_reached on goal.id = goal_reached.goal_id
left join game on goal_reached.game_id = game.id;

![image](https://github.com/user-attachments/assets/a16bf5b4-358a-44d7-b624-4cb3eb386a47)


select name
from country
where iso_country in(
select iso_country
from airport
where name like "Satsuma%");

![image](https://github.com/user-attachments/assets/d9ba2197-ce92-4d3f-99ca-6bae725c343c)


select name
from airport
where iso_country in(
select iso_country
from country
where name = "Monaco");

![image](https://github.com/user-attachments/assets/6578e137-25cc-4090-a2d5-94200b0b8168)


select screen_name
from game
where id in(
select game_id
from goal_reached
where goal_id in(
select id
from goal
where name = "CLOUDS")
);

![image](https://github.com/user-attachments/assets/ee88faa8-d700-46d1-b4a9-f5131fbd0fb7)


select name
from country
where iso_country not in(
select iso_country
from airport);

![image](https://github.com/user-attachments/assets/4bdaa1f8-52df-4f04-9044-21e857417061)


select name
from goal
where id not in(
select goal_id
from goal_reached
where game_id in(
select id
from game
where screen_name = "Heini")
);

![image](https://github.com/user-attachments/assets/b5e9761d-09d5-4ede-9a29-f28a4cbd1750)

# Viikko 4


select max(elevation_ft)
from airport;

![image](https://github.com/user-attachments/assets/fbadb85d-d1c5-4425-9d90-230f69584e11)


select country.continent, count(*)
from country
group by country.continent;

![image](https://github.com/user-attachments/assets/83950314-63dc-490c-8e6e-68077218d681)


select screen_name, count(*)
from game, goal_reached
where id = game_id
group by screen_name;

![image](https://github.com/user-attachments/assets/80caa9eb-1d17-493c-8aa8-670f747a2002)


select screen_name
from game
where co2_consumed in(
select min(co2_consumed)
from game);

![image](https://github.com/user-attachments/assets/d676dfeb-b641-47ec-a37a-4f5f1fa150ab)


select country.name, count(*)
from country, airport
where country.iso_country = airport.iso_country
group by country.iso_country
order by count(*) desc
limit 50;

![image](https://github.com/user-attachments/assets/f9f6994f-375c-4034-8514-ac657ca19f3f)


select country.name
from country, airport
where country.iso_country = airport.iso_country
group by country.iso_country
having count(*) > 1000;

![image](https://github.com/user-attachments/assets/00cedf05-504e-48cb-9263-104d5ddef1ce)


select airport.name
from airport
where elevation_ft in(
select max(elevation_ft)
from airport);

![image](https://github.com/user-attachments/assets/f79c0cfc-48fb-45c0-a068-8c851e6a7a7b)


select country.name
from country
where country.iso_country in(
select airport.iso_country
from airport
where elevation_ft in(
select max(elevation_ft)
from airport)
);

![image](https://github.com/user-attachments/assets/3a100f18-874f-4f62-9eed-a44d2b154229)


select count(*)
from game, goal_reached
where id = game_id and screen_name = "Vesa"
group by screen_name;

![image](https://github.com/user-attachments/assets/de28904f-785d-4380-b22d-27c753fd043c)


select name
from airport
where latitude_deg in(
select min(latitude_deg)
from airport);

![image](https://github.com/user-attachments/assets/a02b4c0b-9002-4ce9-863c-260e24184ba7)

delete from goal_reached;
select * from goal_reached;


delete from game;
select * from game;

# Viikko 5 / Tietokannan suunnittelu harjoitukset

1.
ident

2.
country

3.
a) Maassa voi olla monta lentokenttää

4.
Tosi

5.
Epätosi

6.
b) country-tauluun tulee viiteavain airport-tauluun

7.
a) game-tauluun tulee viiteavain airport-tauluun

8.
Tosi

9.
c) yhteyden salmiakista tulee oma taulunsa

10.
a) viiteavain sekä goal-tauluun että game-tauluun
