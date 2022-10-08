function CheckLuhn(purportedCC: String): Boolean;
var
  i: Integer;
  Sum: Integer;
  Digit: Integer;
begin
  Sum := 0;
  for i := Length( purportedCC ) downto 1 do begin
    Digit := Ord( purportedCC[ i ] ) - Ord( '0' );
	if not(Odd( i )) then begin
	  Digit := Digit * 2;
	  if (Digit > 9) then Digit := Digit - 9;
        end;
    Inc( Summ, Digit );
  end;
  Result := Summ mod 10 = 0;
end;
En Python:

def is_luhn_valid(cc): #Parametro ejemplo 5256783371567695

    num = map(int, str(cc))
    return sum(num[::-2] + [sum(divmod(d * 2, 10)) for d in num[-2::-2]]) % 10 == 0
