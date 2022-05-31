# DATABASE
22-1 DATABASE

/*프로시저를 사용한 구구단*/

        DELIMITER$$ /*SQL 쿼리문재정의 -; 구문*/
                CREATEPROCEDURE gugudan() /*프로시저(구구단)이름 정의*/
                BEGIN /*시작*/
                      DECLARE str varchar(100); /*변수선언, 문자열 타입 varchar*/
                      DECLARE i int; /*변수선언,i 타입 정수*/
                      DECLARE k int; /*변수선언,k 타입 정수*/
                      set i= 2; /*초기화 2부터 세팅,구구단의 단*/ 
    
                        WHILE(i<10)DO----------------WHILE문 2~9단까지
                                SET str = '';---------------초기화 공백 문자열
                                SET k = 1;----------------초기화 1부터 세팅,구구단의 수
        
                        WHILE(k<10) DO------------WHILE문 1~9수까지
                                SET str = concat(str,' ', i,'X', k, '=', i*k);출력 문자열 세팅
                                SET k = k + 1;---------증감연산 1~9까지 수증감
                        END WHILE;---------------WHILE문 종료
                SET ii+ 1;-----------------증감연산 2~9단까지 단증감
                INSERT into GUGU VALUES(str);--GUGU테이블에 삽입 재반복
                END WHILE;------------------WHILE문 종료
        END$$--------------------------코드 종료
