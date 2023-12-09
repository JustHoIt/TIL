# SQL
SQL이란 'Structured Query Language'의 약자로, 데이터베이스에서 데이터를 추출하고 조작하는 데이터 처리 언어이다.

## SQL 종류
- DDL(Data Definition Language) -데이터 정의 언어
- DML(Data Manipulation Language) - 데이터 조작 언어
- DCL(Data Control Language) - 데이터 제어 언어
- DQL(Data Query Language) - 데이터 질의 언어
- TCL(Transaction Control Language) - 트랜젝션 제어어


## 1. DDL(Data Definition Language) -데이터 정의 언어
### 1) CREATE
```
CREATE TABLE testUser(
id INT(11) NOT NULL AUTO_INCREMENT,
name VARCHAR(20) NOT NULL,
email VARCHAR(30) NOT NULL,
birth DATETIME NULL,
phone VARCHAR(20) NULL,
);
```
### 2) ALTER
- 수정
### 3) DROP
- 삭제
### 4) TRUNCATE
- 테이블 구조를 남기고 데이터 삭제
```
TRUNCATE TABLE testUser;
```
### 5) RENAME
- 테이블명 or 칼럼명 변경

## 2. DML(Data Manipulation Language) - 데이터 조작 언어
### 1) INSERT
- 데이터 추가
### 2) UPDATE
- 데이터 수정
### 3) DELETE
- 데이터 삭제

## 3. DQL(Data Query Language) - 데이터 질의 언어
### 1) SELECT
### 2) WHERE
```
SELECT *
FROM birth
WHERE from_date = '1999-01-01';

SELECT *
FROM birth
WHERE from_date > '2005-05-05';

SELECT *
FROM birth
WHERE from_date BETWEEN '2003-03-03' AND '2004-04-04';

SELECT *
FROM birth
WHERE MONTH(from_date) = 8 AND YEAR(from_date) = 2023;

SELECT *
FROM birth
WHERE from_ date >= CURDATE() - INTERVAL 10 YEAR
```
### 3) DISTINCT
### 4) GROUP BY
### 5) ORDER BY

## 4. DCL(Data Control Language) - 데이터 제어 언어
### 1) GRANT
- 권한 부여
### 2) REVOKE
- 권한 해제

## 5. TCL(Transaction Control Language) - 트랜젝션 제어어
### 1) COMMIT
### 2) ROLLBACK
