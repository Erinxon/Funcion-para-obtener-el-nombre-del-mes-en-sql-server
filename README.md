# Función para obtener el nombre del mes en SQL SERVER

```sql
create FUNCTION GetMonthName(@date datetime)  
RETURNS varchar(9) 
    AS 
    BEGIN
	DECLARE @Month int = MONTH(@date)
        DECLARE @MonthName varchar(100) = '';  
        set @MonthName = (case 
		when @Month = 1 then 'Enero' 
		when @Month = 2 then 'Febrero' 
		when @Month = 3 then 'Marzo' 
		when @Month = 4 then 'Abril' 
		when @Month = 5 then 'Mayo' 
		when @Month = 6 then 'Junio' 
		when @Month = 7 then 'Julio' 
		when @Month = 8 then 'Agosto' 
		when @Month = 9 then 'Septiembre' 
		when @Month = 10 then 'Octubre' 
		when @Month = 11 then 'Noviembre' 
		else 'Diciembre'
		end)
        RETURN @MonthName; 
    END

SELECT [dbo].GetMonthName(GETDATE())
```
