# sqlisland

Solution of sql island game

SELECT * FROM INHABITANT

SELECT * FROM INHABITANT WHERE state = 'friendly'

SELECT * FROM INHABITANT WHERE state = 'friendly' AND job = 'weaponsmith'

SELECT * FROM INHABITANT WHERE state = 'friendly' AND job LIKE '%smith'

SELECT personid FROM INHABITANT WHERE name = 'Stranger'

SELECT gold FROM INHABITANT WHERE name = 'Stranger'

SELECT * FROM ITEM WHERE owner IS NULL

UPDATE item SET owner=20 WHERE owner IS NULL

SELECT * FROM ITEM WHERE owner = 20

SELECT * FROM INHABITANT WHERE (job = 'dealer' OR job = 'merchant') AND state = 'friendly'

UPDATE item SET owner = 15 WHERE item = 'ring' OR item = 'teapot'

UPDATE inhabitant SET name = 'Astitva' WHERE personid = 20

SELECT * FROM INHABITANT WHERE job = 'baker' ORDER BY gold DESC

SELECT * FROM INHABITANT WHERE job = 'pilot'

SELECT inhabitant.name FROM village,inhabitant WHERE village.chief = inhabitant.personid AND village.name = 'Onionville'

SELECT COUNT(*) FROM inhabitant,village WHERE village.villageid = inhabitant.personid AND (village.name = 'Onionville' AND inhabitant.gender = 'f')

SELECT inhabitant.name FROM inhabitant,village ON village.villageid = inhabitant.villageid WHERE (village.name = 'Onionville' AND inhabitant.gender = 'f')

SELECT SUM(inhabitant.gold) FROM inhabitant,village ON village.villageid = inhabitant.villageid WHERE (job = 'baker' OR job = 'dealer' or job = 'merchant')

SELECT state, AVG(inhabitant.gold) FROM inhabitant GROUP BY state ORDER BY AVG(inhabitant.gold)
DELETE FROM inhabitant WHERE name= 'Dirty Diane'
UPDATE inhabitant SET state = 'friendly' WHERE job = 'pilot'
