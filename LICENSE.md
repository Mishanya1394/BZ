unit Vvod2;

interface
uses
  crt;
type
   zak2 = record
     FIO:string;
     Sale:integer;
     adress:string;
     end;
  procedure VvodZak(var ar2:array of zak2 );
 { procedure save(ar2:array of zak2); }

implementation
procedure VvodZak(var ar2:array of zak2);
var m,i:integer; code:integer; s:string;
begin

 for i:=0 to length(ar2)-1 do
 begin
   repeat
     writeln('Введите ФИО заказчика');
     readln(ar2[i].FIO);
     until (ar2[i].FIO)<>'' ;
   repeat
     writeln('Введите скидку ( в процентах)');
     readln(ar2[i].Sale);
     until (ar2[i].Sale<> 0);
     repeat
     writeln('Введите адрес доставки');
     readln(ar2[i].adress);
     until ar2[i].adress<> '';
     end;
 end;
procedure save(ar2:array of zak2);
var f:text; s:string;
i,m,k:integer;
begin
 assign(f,'Zakaz.txt');
 rewrite(f);
for i := 0 to length(Ar2)-1 do
writeln(f, ar2[i].FIO, '  ','ФИО заказчика ', ar2[i].sale ,'%'
, ar2[i].adress, 'адресс');
close(f);
 end;
end.
