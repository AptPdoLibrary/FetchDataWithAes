# AptPdoLibrary - FetchDataWithAes

How to Use FetchDataWithAes function ->

Call function :

Example :-

$Condtion = "Username::::$Username::,::UserId::::$UserId"; (It is use for condtion like Where Username equal to $Username, If Given column not available in table then it return an error)

none - Use none for get data from all contion of given table

$FatchColumn = 'Name::::Class::::Gander'; (It is use to which get Data from table. If Given column not available in table then it return an error)

DatabaseConnection :-
$DatabaseConnection is a pdo connection object

DbTableName :-
$DbTableName = 'TableName';

EncodeAndEncryptPass :-
$EncodeAndEncryptPass = 'password';
It is use to decrypt the data. It must be equal to which is used to encrypt data at insert time 

CheckFor :-
$CheckFor = 'any';
any :- It indicate if any one conditoion($SearchData) satisfied then function return data

all :- It indicate if all conditoion($SearchData) satisfied then function return data

NotEqualAny :- It indicate if any one conditoion($SearchData) not satisfied then function return data

NotEqualAll :- It indicate if all conditoion($SearchData) not satisfied then function return data

StartLikeAny :- It indicate if any condtion value match with entire/staring value of given column then it return data

LikeLastAny :- It indicate if any condtion value match with entire/last value of given column then it return data 

StartLikeLastAny :- It indicate if any condtion value match with entire/starting/last/middle value of given column then it return data

FetchCount :-
$FetchCount = 'all';
By default FetchCount  is NULL. If FetchCount is null then it return only one row in reasult

all - Then it return all rows which satisfied the given condtion($SearchData)

$Response = FetchDataWithAes($Condtion,$FatchColumn,$DatabaseConnection,$DbTableName,$EncodeAndEncryptPass,$CheckFor = 'any' ,=$FetchCount = NULL);

Check Response :
if($Response['status'] === 'Success' && $Response['code'] === 200){
  #Code... (After data featch successfully into database)
}else if($Response['code'] === 404){
  #Code... (After Search data (Given condtion) not found in database)
}else{
  #Code...  (After data found process failed)
}
