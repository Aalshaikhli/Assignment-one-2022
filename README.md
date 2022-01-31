# Assignment-one-2022
Alshaikhli Alaa 

CREATE TABLE aliases (
alias_ID NUMBER(6),
criminal_ID NUMBER(6,0),
alias_col VARCHAR2(10)
);
CREATE TABLE  criminals (
criminal_ID NUMBER(6,0),
last_col VARCHAR2(15),
first_col VARCHAR2(10),
street VARCHAR2(30),
city VARCHAR2(20),
state CHAR(2),
zip CHAR(5),
phone CHAR(10),
v_status CHAR(1) DEFAULT 'N',
p_status CHAR(1) DEFAULT 'N'
);
CREATE TABLE crimes (
crime_ID NUMBER(9,0),
criminal_ID NUMBER(6,0),
classification CHAR(1),
data_changed DATE DEFAULT SYSDATE,
status CHAR(2),
hearing_date DATE,
appeal_cut_date DATE,
);
CREATE TABLE sentences (
sentence_ID NUMBER(6),
criminal_ID NUMBER(6,0),
type_col CHAR(1),
prob_ID NUMBER(5),
start_date DATE,
end_date DATE,
violations NUMBER(3)
);
CREATE TABLE prob_officers (
prob_ID NUMBER(5),
last_col VARCHAR2(15),
first_col VARCHAR2(10),
street VARCHAR2(30),
city VARCHAR2(20),
state CHAR(2),
zip CHAR(5,0),
phone CHAR(10,0),
email VARCHAR2(30),
status CHAR(1) DEFAULT 'A'
);
CREATE TABLE crime_charges (
charge_ID NUMBER(10,0),
crime_ID NUMBER(9,0),
crime_code NUMBER(3,0),
charge_status CHAR(2),
fine_amount NUMBER(7,2),
court_fee NUMBER(7,2),
amount_paid NUMBER(7,2),
pay_due_date DATE
);
CREATE TABLE crime_officers (
crime_ID NUMBER(9,0),
officer_ID NUMBER(8,0)
);
CREATE TABLE officers (
officer_ID NUMBER(8,0),
last_col VARCHAR2(15),
first_col VARCHAR2(10),
precinct CHAR(4),
badge VARCHAR2(14),
phone CHAR(10,0),
status CHAR(1) DEFAULT 'A'
);
CREATE TABLE appeals (
appeal_ID NUMBER(5),
crime_ID NUMBER(9,0),
filing_date DATE,
hearing_date DATE,
status CHAR(1) DEFAULT 'P'
);
CREATE TABLE crime_codes (
crime_code NUMBER(3,0),
code_description VARCHAR2(30)
);

/* Section B */

ALTER TABLE crimes
MODIFY classification DEFAULT 'U';

ALTER TABLE crimes
ADD(date_recorded DATE DEFAULT SYSDATE);

ALTER TABLE prob_officers
ADD(pager# NUMBER(10));

ALTER TABLE aliases
MODIFY(alias_col VARCHAR2(20));
