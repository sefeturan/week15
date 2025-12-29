SELECT musteri_kodu, MAX(sut_lt) AS Expr1
FROM   alinan_sut
GROUP BY musteri_kodu
ORDER BY Expr1 DESC




SELECT        SUM(sut_tutar) AS Expr1
FROM            alinan_sut
WHERE        (tarih BETWEEN '2014 - 04 - 01' AND '2014 - 04 - 30') AND (musteri_kodu = 203)



SELECT        musteri_kodu, SUM(sut_lt) AS Expr1
FROM            alinan_sut
GROUP BY musteri_kodu
ORDER BY Expr1 DESC


create procedure bring_annually
@date1 date,  
@date2 date
as 
begin
 select sum(sut_lt) 
from alinan_sut
where tarih between @date1 and @date2

end

bring_annually '2014-04-01', '2015-04-01'


