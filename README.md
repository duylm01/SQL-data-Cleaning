# SQL-data-Cleaning
## VIEW 10 FIRST OF TABLE
```sql
SELECT *
FROM club_member_info
LIMIT 10;
```
### Result

|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|
|addie lush|40|married|alush0@shutterfly.com|254-389-8708|3226 Eastlawn Pass,Temple,Texas|Assistant Professor|7/31/2013|
|      ROCK CRADICK|46|married|rcradick1@newsvine.com|910-566-2007|4 Harbort Avenue,Fayetteville,North Carolina|Programmer III|5/27/2018|
|Sydel Sharvell|46|divorced|ssharvell2@amazon.co.jp|702-187-8715|4 School Place,Las Vegas,Nevada|Budget/Accounting Analyst I|10/6/2017|
|Constantin de la cruz|35||co3@bloglines.com|402-688-7162|6 Monument Crossing,Omaha,Nebraska|Desktop Support Technician|10/20/2015|
|  Gaylor Redhole|38|married|gredhole4@japanpost.jp|917-394-6001|88 Cherokee Pass,New York City,New York|Legal Assistant|5/29/2019|
|Wanda del mar       |44|single|wkunzel5@slideshare.net|937-467-6942|10864 Buhler Plaza,Hamilton,Ohio|Human Resources Assistant IV|3/24/2015|
|Joann Kenealy|41|married|jkenealy6@bloomberg.com|513-726-9885|733 Hagan Parkway,Cincinnati,Ohio|Accountant IV|4/17/2013|
|   Joete Cudiff|51|divorced|jcudiff7@ycombinator.com|616-617-0965|975 Dwight Plaza,Grand Rapids,Michigan|Research Nurse|11/16/2014|
|mendie alexandrescu|46|single|malexandrescu8@state.gov|504-918-4753|34 Delladonna Terrace,New Orleans,Louisiana|Systems Administrator III|3/12/1921|
| fey kloss|52|married|fkloss9@godaddy.com|808-177-0318|8976 Jackson Park,Honolulu,Hawaii|Chemical Engineer|11/5/2014|

## MOFIDY full_name COLUMN
```sql
SELECT TRIM(full_name)
FROM club_member_info;

UPDATE club_member_info
SET full_name = TRIM(full_name);

SELECT UPPER(full_name)
FROM club_member_info;
LIMIT 10;

UPDATE club_member_info
SET full_name = UPPER(full_name);
```
### Result

|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|
|ADDIE LUSH|40|married|alush0@shutterfly.com|254-389-8708|3226 Eastlawn Pass,Temple,Texas|Assistant Professor|7/31/2013|
|ROCK CRADICK|46|married|rcradick1@newsvine.com|910-566-2007|4 Harbort Avenue,Fayetteville,North Carolina|Programmer III|5/27/2018|
|SYDEL SHARVELL|46|divorced|ssharvell2@amazon.co.jp|702-187-8715|4 School Place,Las Vegas,Nevada|Budget/Accounting Analyst I|10/6/2017|
|CONSTANTIN DE LA CRUZ|35||co3@bloglines.com|402-688-7162|6 Monument Crossing,Omaha,Nebraska|Desktop Support Technician|10/20/2015|
|GAYLOR REDHOLE|38|married|gredhole4@japanpost.jp|917-394-6001|88 Cherokee Pass,New York City,New York|Legal Assistant|5/29/2019|
|WANDA DEL MAR|44|single|wkunzel5@slideshare.net|937-467-6942|10864 Buhler Plaza,Hamilton,Ohio|Human Resources Assistant IV|3/24/2015|
|JOANN KENEALY|41|married|jkenealy6@bloomberg.com|513-726-9885|733 Hagan Parkway,Cincinnati,Ohio|Accountant IV|4/17/2013|
|JOETE CUDIFF|51|divorced|jcudiff7@ycombinator.com|616-617-0965|975 Dwight Plaza,Grand Rapids,Michigan|Research Nurse|11/16/2014|
|MENDIE ALEXANDRESCU|46|single|malexandrescu8@state.gov|504-918-4753|34 Delladonna Terrace,New Orleans,Louisiana|Systems Administrator III|3/12/1921|
|FEY KLOSS|52|married|fkloss9@godaddy.com|808-177-0318|8976 Jackson Park,Honolulu,Hawaii|Chemical Engineer|11/5/2014|

## MODIFY age COLUMN
```sql
SELECT age
FROM club_member_info
WHERE age > 100 

SELECT SUBSTR(age,2) #loại bỏ số đầu tiên của tuổi chỉ lấy bắt đầu từ số thứ 2
FROM club_member_info
WHERE age>100;

UPDATE club_member_info
SET age = SUBSTR(age,2)
WHERE age>100;

SELECT *
FROM club_member_info
WHERE age IS NULL OR age ='';

SELECT ROUND(AVG(age))
FROM club_member_info;

UPDATE club_member_info
SET age = 42
WHERE age IS NULL OR age = '';

# FINAL CHECK
SELECT *
FROM club_member_info
WHERE age IS NULL OR age ='';

```

### RESULT

|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|

## MODIFY martial_status COLUMN
```sql
# Count martial_status

SELECT martial_status, COUNT(*)  AS count
FROM club_member_info
GROUP BY martial_status;

# We can see the martial_status almost is 'divorced'
# So I will fill the NULL value = divorced

UPDATE club_member_info
SET martial_status = 'divorced'
WHERE martial_status IS NULL OR martial_status = '';

# Final check

SELECT martial_status
FROM club_member_info
WHERE martial_status IS NULL OR martial_status = '';

```
### Result 

|martial_status|
|--------------|






