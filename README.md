# d
SELECT ENAME, SAL FROM SCOTT.EMP;
SELECT ENAME, DEPTNO FROM SCOTT.EMP;
SELECT * FROM SCOTT.EMP;
SELECT COMM, SAL, MGR, ENAME FROM SCOTT.EMP;
ALIAS :
SELECT ENAME, SAL AS SALARY, COMM AS COMMISSION, MGR AS MANAGER FROM SCOTT.EMP;
SELECT ENAME, SAL SALARY, COMM COOMI, MGR MANAGER FROM SCOTT.EMP;
SELECT ENAME "EMPLOYEE", SAL " EMP EARNINGS", MGR "MANAGERS" FROM SCOTT.EMP;
EXPRESSIONS:
SELECT ENAME, JOB, SAL, SAL * 12 FROM SCOTT.EMP;
SELECT ENAME, JOB, SAL, COMM, SAL + COMM FROM SCOTT.EMP;
SELECT ENAME, JOB, SAL, COMM, SAL + NVL(COMM, 0) FROM SCOTT.EMP;
SELECT 1 FROM SCOTT.EMP;
SELECT 2*3 FROM SCOTT.EMP;
SELECT 2+3, 2*3, 2-3, 2/3 FROM SCOTT.EMP;
LITERALS:
SELECT ENAME, 'IS WORKING AS', JOB, 'IN DEPTNO', DEPTNO FROM SCOTT.EMP; 
SELECT ENAME || JOB || SAL FROM SCOTT. EMP;
SELECT ENAME || ' IS WORKING AS' || JOB || ' IN DEPT' || DEPTNO || ' AND EARNING ' || SAL " mY 
eMPLOYEES" FROM SCOTT.EMP;
DISTINCT:
SELECT JOB FROM SCOTT.EMP;
SELECT DISTINCT JOB FROM SCOTT.EMP;
SELECT DISTINCT DEPTNO FROM SCOTT.EMP;
SELECT DISTINCT DEPTNO, JOB FROM SCOTT.EMP;
ORDER BY
SELECT * FROM SCOTT.EMP;
SELECT * FROM SCOTT.EMP ORDER BY EMPNO;
SELECT * FROM SCOTT.EMP ORDER BY EMPNO DESC;
SELECT * FROM SCOTT.EMP ORDER BY DEPTNO;
SELECT * FROM SCOTT.EMP ORDER BY DEPTNO, JOB;
SELECT * FROM SCOTT.EMP ORDER BY 3;
SELECT ENAME, JOB,SAL,DEPTNO FROM SCOTT.EMP ORDER BY 2;
SELECT ENAME,JOB,SAL,COMM,SAL*12 FROM SCOTT.EMP ORDER BY SAL*12;
SELECT ENAME,JOB,SAL,COMM, SAL*12 "ANNUAL" FROM SCOTT.EMP ORDER BY "ANNUAL";
WHERE 
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE DEPTNO=20;
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE JOB='MANAGER';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE DEPTNO <> 20;
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE DEPTNO IN (10,30);
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE JOB IN ('MANAGER', 'CLERK');
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE DEPTNO NOT IN (10,30);
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE SAL > 2000;
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE SAL >= 2000;
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE SAL < 3000;
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE SAL <= 3000;
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE SAL BETWEEN 2000 AND 3000;
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE SAL NOT BETWEEN 2000 AND 3000;
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE ENAME LIKE 'S%';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE ENAME LIKE '%S';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE ENAME LIKE '%S%';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE ENAME LIKE '____';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE ENAME LIKE '__A%';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE ENAME NOT LIKE 'S%';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE DEPTNO=20 AND JOB='MANAGER';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE DEPTNO=20 OR JOB='MANAGER';
SELECT ENAME,JOB,SAL,DEPTNO FROM SCOTT.EMP WHERE NOT (DEPTNO=20);
SET OPERATORS
CONDITIONS : QUERIES MUST CONTAIN SAME NUMBER OF COLUMS SELECTED, AND CORRESPONING 
COLUMN MUST BE OF SAME TYPE
UNION
SELECT ENAME, JOB,SAL ,COMM, DEPTNO FROM SCOTT.EMP WHERE DEPTNO=20
UNION
SELECT ENAME, JOB,SAL ,COMM, DEPTNO FROM SCOTT.EMP WHERE JOB='MANAGER';
UNION ALL
SELECT ENAME, JOB,SAL ,COMM, DEPTNO FROM SCOTT.EMP WHERE DEPTNO=20
UNION ALL
SELECT ENAME, JOB,SAL ,COMM, DEPTNO FROM SCOTT.EMP WHERE JOB='MANAGER';
INTERSECT
SELECT ENAME, JOB,SAL ,COMM, DEPTNO FROM SCOTT.EMP WHERE DEPTNO=20
INTERSECT
SELECT ENAME, JOB,SAL ,COMM, DEPTNO FROM SCOTT.EMP WHERE JOB='MANAGER';
MINUS
SELECT ENAME, JOB,SAL ,COMM, DEPTNO FROM SCOTT.EMP WHERE DEPTNO=20
MINUS
SELECT ENAME, JOB,SAL ,COMM, DEPTNO FROM SCOTT.EMP WHERE JOB='MANAGER';
FUNCTIONS
SINGLE ROW FUNCTIONS [CHAR , NUMBER, DATE , CONVERSION]
GROUP FUNCTIONS [SUM, AVERAGE, MAX , MIN, STANDARD DEVIATION , VARIANCE] AND GROUP BY 
CLAUSE AND HAVING
SINGLE ROW FUNCTIONS:
CHARACTER FUNCTIONS
SELECT ENAME, LENGTH(ENAME), JOB,SAL ,DEPTNO FROM SCOTT.EMP;
SELECT ENAME, LOWER(ENAME) , JOB,SAL ,DEPTNO FROM SCOTT.EMP;
SELECT ENAME, UPPER(ENAME) , JOB,SAL ,DEPTNO FROM SCOTT.EMP;
SELECT ENAME, INITCAP(ENAME) , JOB,SAL ,DEPTNO FROM SCOTT.EMP;
SELECT ENAME, SUBSTR(ENAME,3,4) , JOB,SAL ,DEPTNO FROM SCOTT.EMP;
SELECT ENAME, REPLACE(ENAME,'SMITH','FRIEND') , JOB,SAL ,DEPTNO FROM SCOTT.EMP;
SELECT ENAME, DECODE(JOB, 'MANAGER','MGR', 'CLERK', 'CLK', 'OTHERS'),SAL ,DEPTNO FROM 
SCOTT.EMP;
SELECT ENAME, TRANSLATE(ENAME,'S','Z') , JOB,SAL ,DEPTNO FROM SCOTT.EMP;
NUMBER FUNCTIONS
SELECT ABS(-4.5) FROM DUAL;
SELECT SQRT(81) FROM DUAL;
SELECT POWER(2,3) FROM DUAL;
SELECT LOG(10,10) FROM DUAL;
SELECT EXP(-1) FROM DUAL;
SELECT GREATEST(2,3) FROM DUAL;
SELECT LEAST(2,3) FROM DUAL;
SELECT ROUND(56.67) FROM DUAL;
SELECT ROUND(56.11) FROM DUAL;
SELECT ROUND(565.678, 0) FROM DUAL;
SELECT ROUND(565.678, -1) FROM DUAL;
SELECT ROUND(562.678, -1) FROM DUAL;
SELECT ROUND(565.678, -2) FROM DUAL;
SELECT ROUND(535.678, -2) FROM DUAL;
SELECT ROUND(565.678, -3) FROM DUAL;
SELECT ROUND(365.678, -3) FROM DUAL;
SELECT ROUND(365.678, 3) FROM DUAL;
SELECT ROUND(365.678, 2) FROM DUAL;
SELECT ROUND(365.678, 1) FROM DUAL;
SELECT CEIL(365.657) FROM DUAL;
SELECT FLOOR(365.657) FROM DUAL;
DATE FUNCTIONS
SELECT SYSDATE FROM DUAL;
SELECT MONTHS_BETWEEN(SYSDATE, '25-JAN-22') FROM DUAL;
SELECT NEXT_DAY(SYSDATE,'FRIDAY') FROM DUAL;
SELECT LAST_DAY(SYSDATE) FROM DUAL;
SELECT TO_CHAR(SYSDATE, 'HH:MM:SS') FROM DUAL;
GROUP FUNCTIONS [ GROUP BY CONDITIONS. SELECT ONLY THOSE COLUMNS THAT ARE PART OF 
GROUP BY CLAUSE OR APPLIED WITH GROUP FUNCTIONS ]
SELECT SUM(SAL) FROM SCOTT.EMP;
SELECT AVG(SAL) FROM SCOTT.EMP;
SELECT MAX(SAL) FROM SCOTT.EMP;
SELECT MIN(SAL) FROM SCOTT.EMP;
SELECT STDDEV(SAL) FROM SCOTT.EMP;
SELECT VARIANCE(SAL) FROM SCOTT.EMP;
SELECT DEPTNO, SUM(SAL) FROM SCOTT.EMP GROUP BY DEPTNO;
SELECT JOB, AVG(SAL) FROM SCOTT.EMP GROUP BY JOB;
SELECT DEPTNO, MAX(SAL) FROM SCOTT.EMP GROUP BY DEPTNO;
SELECT DEPTNO, JOB, SUM(SAL) FROM SCOTT.EMP GROUP BY DEPTNO,JOB;
SELECT COUNT(*) FROM SCOTT.EMP;
SELECT COUNT(EMPNO) FROM SCOTT.EMP;
SELECT COUNT(COMM) FROM SCOTT.EMP;
SELECT DEPTNO, JOB, COUNT(*) FROM SCOTT.EMP GROUP BY DEPTNO, JOB ORDER 
SELECT DEPTNO, AVG(SAL) FROM SCOTT.EMP GROUP BY DEPTNO HAVING AVG(SAL) > 2000;
SELECT DEPTNO, AVG(SAL) FROM SCOTT.EMP HAVING AVG(SAL) > 2000 GROUP BY DEPTNO;
SELECT DEPTNO,AVG(SAL) , COUNT(*) FROM SCOTT.EMP GROUP BY DEPTNO HAVING COUNT(*) > 
3;BY DEPTNO;
SELECT ROUND(AVG(SAL)) , DEPTNO FROM SCOTT.EMP GROUP BY DEPTNO;
SELECT DEPTNO, JOB, SUM(SAL) FROM SCOTT.EMP WHERE JOB NOT IN ('PRESIDENT') HAVING 
SUM(SAL) > 1500 GROUP BY DEPTNO, JOB ORDER BY DEPTNO;
SELECT DEPTNO, JOB, SUM(SAL), SUM(COMM) FROM SCOTT.EMP GROUP BY CUBE(DEPTNO, JOB) 
ORDER BY DEPTNO;
SELECT DEPTNO, JOB, SUM(SAL) FROM SCOTT.EMP GROUP BY ROLLUP(DEPTNO, JOB) ORDER BY 
DEPTNO;
TOP N ANALYSIS
ROWNUM IS PSEUDO COLUMN TO DISPLAY THE ROW NUMBER
SELECT ROWNUM, ENAME,JOB,SAL FROM SCOTT.EMP;
SELECT ROWNUM, ENAME,JOB,SAL FROM ( SELECT * FROM SCOTT.EMP ORDER BY SAL DESC) WHERE 
ROWNUM <=5;
SELECT ROWNUM, ENAME,JOB,SAL FROM ( SELECT * FROM SCOTT.EMP ORDER BY SAL ) WHERE 
ROWNUM <=5;
SELECT ROWNUM, ENAME,JOB,COMM FROM ( SELECT * FROM SCOTT.EMP ORDER BY COMM ) 
WHERE ROWNUM <=5;
JOINS : SELECTING DATA FROM MORE THAN ONE TABLE
CROSS JOIN / CARTISIAN PRODUCT
SELECT ENAME, JOB, SAL, DNAME, LOC FROM SCOTT.EMP, SCOTT.DEPT;
SELECT ENAME, JOB, SAL, DNAME, LOC FROM SCOTT.EMP CROSS JOIN SCOTT.DEPT;
EQUI JOIN
SELECT ENAME, JOB, SAL, DNAME, LOC, SCOTT.EMP.DEPTNO FROM SCOTT.EMP , SCOTT.DEPT WHERE 
SCOTT.EMP.DEPTNO = SCOTT.DEPT.DEPTNO;
NATURAL JOIN
SELECT ENAME, JOB, SAL, DNAME, LOC FROM SCOTT.EMP NATURAL JOIN SCOTT.DEPT;
TABLE ALIAS:
SELECT ENAME, JOB, SAL, DNAME, LOC, E.DEPTNO FROM SCOTT.EMP E, SCOTT.DEPT D WHERE 
E.DEPTNO = D.DEPTNO;
OUTER JOINS
SELECT ENAME, JOB, SAL, DNAME, LOC, E.DEPTNO, D.DEPTNO FROM SCOTT.EMP E, SCOTT.DEPT D 
WHERE E.DEPTNO (+) = D.DEPTNO;
SELECT ENAME, JOB, SAL, DNAME, LOC, E.DEPTNO, D.DEPTNO FROM SCOTT.EMP E, SCOTT.DEPT D 
WHERE E.DEPTNO = D.DEPTNO (+);
SELECT ENAME, JOB, SAL, DNAME, LOC, E.DEPTNO, D.DEPTNO FROM SCOTT.EMP E LEFT OUTER JOIN 
SCOTT.DEPT D ON E.DEPTNO=D.DEPTNO;
SELECT ENAME, JOB, SAL, DNAME, LOC, E.DEPTNO, D.DEPTNO FROM SCOTT.EMP E RIGHT OUTER JOIN 
SCOTT.DEPT D ON E.DEPTNO=D.DEPTNO;
SELECT ENAME, JOB, SAL, DNAME, LOC, E.DEPTNO, D.DEPTNO FROM SCOTT.EMP E FULL OUTER JOIN 
SCOTT.DEPT D ON E.DEPTNO=D.DEPTNO;
NON EQUI JOIN
SELECT ENAME,JOB,SAL ,D.DEPTNO FROM SCOTT.EMP E, SCOTT.DEPT D WHERE SAL BETWEEN 1000 
AND 2000;
CREATE TABLE SALGRADE(GRADE NUMBER, LOSAL NUMBER, HISAL NUMBER);
INSERT INTO SALGRADE VALUES(2, 1001, 2000);
INSERT INTO SALGRADE VALUES(3, 2001, 3000);
INSERT INTO SALGRADE VALUES(4, 3001, 4000);
INSERT INTO SALGRADE VALUES(5, 4001, 5000);
SELECT * FROM SALGRADE;
SELECT E.ENAME,E.JOB,E.SAL ,E.DEPTNO , S.GRADE FROM SCOTT.EMP E, SALGRADE S WHERE SAL 
BETWEEN LOSAL AND HISAL;
DELETE FROM SALGRADE WHERE GRADE=1;
SELF JOIN
SELECT E.ENAME , M.ENAME FROM SCOTT.EMP E, SCOTT.EMP M WHERE M.EMPNO = E.MGR;
JOINING MORE THAN 2 TABLES:
SELECT ENAME, JOB,SAL , DNAME, LOC, GRADE FROM SCOTT.EMP, SCOTT.DEPT, SALGRADE WHERE 
SCOTT.EMP.DEPTNO = SCOTT.DEPT.DEPTNO AND SCOTT.SAL BETWEEN LOSAL AND HISAL;
SUBQUERIES
SELECT * FROM SCOTT.EMP WHERE SAL > (SELECT SAL FROM SCOTT.EMP WHERE ENAME='ADAMS');
SELECT * FROM SCOTT.EMP WHERE JOB = (SELECT JOB FROM SCOTT.EMP WHERE ENAME='BLAKE');
SELECT * FROM SCOTT.EMP WHERE SAL > (SELECT AVG(SAL) FROM SCOTT.EMP);
SELECT * FROM SCOTT.EMP WHERE SAL >= (SELECT MAX(SAL) FROM SCOTT.EMP);
SELECT * FROM SCOTT.EMP WHERE SAL IN (SELECT MAX(SAL) FROM SCOTT.EMP GROUP BY DEPTNO);
SELECT * FROM SCOTT.EMP WHERE SAL IN (SELECT MIN(SAL) FROM SCOTT.EMP GROUP BY DEPTNO);
SELECT * FROM SCOTT.EMP WHERE SAL IN (SELECT MAX(SAL) FROM SCOTT.EMP GROUP BY JOB);
SELECT * FROM SCOTT.EMP WHERE (DEPTNO, SAL) IN (SELECT DEPTNO, MAX(SAL) FROM SCOTT.EMP 
GROUP BY DEPTNO);
SELECT * FROM SCOTT.EMP WHERE EXISTS (SELECT * FROM SCOTT.EMP WHERE DEPTNO=40) ;
SELECT ENAME , JOB , (SELECT SAL FROM SCOTT.EMP WHERE ENAME='SCOTT') FROM SCOTT.EMP;
SELECT ENAME,JOB,SAL FROM (SELECT * FROM SCOTT.EMP WHERE DEPTNO=20);
INSERT UPATE DELETE
INSERT INTO SCOTT.EMP(EMPNO, ENAME, SAL, DEPTNO,JOB) VALUES(9999, 
'DINESH','3456','40','MANAGER');
INSERT INTO SCOTT.EMP(EMPNO, ENAME, SAL, DEPTNO,JOB) VALUES(9999, 
'DINESH',3456,40,'MANAGER');
UPDATE SCOTT.EMP SET SAL= 5000 , JOB='MANAGER' WHERE ENAME='SCOTT';
DELETE FROM SCOTT.EMP WHERE DEPTNO=40;
CREATE ALTER DROP
CREATE TABLE STUDENTS(SID NUMBER, SNAME VARCHAR2(20), SMARKS NUMBER);
ALTER TABLE STUDENTS ADD(SPROG VARCHAR2(20));
ALTER TABLE STUDENTS MODIFY(SPROG VARCHAR2(30));
ALTER TABLE STUDENTS DROP COLUMN SPROG;
DROP TABLE STUDENTS;
