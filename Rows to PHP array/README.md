# Rows to PHP array

Simple formula to concatenate rows into a PHP array [[Sheet](https://docs.google.com/spreadsheets/d/1deAthdVwhfH_h2H79O52Bhm5guHsJ5wZg3thnyWoyqI/edit#gid=0)].

![Sheet](https://github.com/dansysanalyst/Google-Sheets/blob/main/Rows%20to%20PHP%20array/sheet.png "Sheet")

#### Formula
```sql
=CONCATENATE(
    "[",
      "'",REGEXREPLACE(REGEXREPLACE(REGEXREPLACE(SUBSTITUTE(LOWER(A$1),"'","\'"),"\s+","_"),"\n",""),"[^A-Za-z_]+","")
,"' => '",regexreplace(SUBSTITUTE(A2,"'","\'"),"\n",""),"', ",
      "'",REGEXREPLACE(REGEXREPLACE(REGEXREPLACE(SUBSTITUTE(LOWER(B$1),"'","\'"),"\s+","_"),"\n",""),"[^A-Za-z_]+","")
,"' => '",regexreplace(SUBSTITUTE(B2,"'","\'"),"\n",""),"', ",
      "'",REGEXREPLACE(REGEXREPLACE(REGEXREPLACE(SUBSTITUTE(LOWER(C$1),"'","\'"),"\s+","_"),"\n",""),"[^A-Za-z_]+","")
,"' => '",regexreplace(SUBSTITUTE(C2,"'","\'"),"\n",""),"', ",
      "'",REGEXREPLACE(REGEXREPLACE(REGEXREPLACE(SUBSTITUTE(LOWER(D$1),"'","\'"),"\s+","_"),"\n",""),"[^A-Za-z_]+","")
,"' => ",TO_PURE_NUMBER(D2),", ",
    "],"
  )
`````
