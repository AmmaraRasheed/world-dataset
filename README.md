# world-dataset

select * from world.city;
select * from world.country;
select * from world.countrylanguage;

SELECT c.Name as CityName, co.Name as CountryName, c.Population
FROM world.city c
JOIN world.country co ON c.CountryCode = co.Code
ORDER BY c.Population DESC
LIMIT 10;

SELECT co.Name as CountryName, COUNT(cl.Language) as OfficialLanguages
FROM world.country co
JOIN world.countrylanguage cl ON co.Code = cl.CountryCode
WHERE cl.IsOfficial = 'T'
GROUP BY co.Name
HAVING COUNT(cl.Language) > 1;

