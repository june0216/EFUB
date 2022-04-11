### 4주차 과제 
# (1) 학사 정보 관리 ERD
<img width="383" alt="20220411_131100" src="https://user-images.githubusercontent.com/76603301/162665394-caa0cf53-b687-47e4-88c3-5ace650fe8bf.png">

# (2) mysql 실습

### a. sws 테이블 생성하기 
```sql
USE efub;

CREATE TABLE sws (
    sws_id BIGINT NOT NULL AUTO_INCREMENT,
    team_name VARCHAR(25),
    PRIMARY KEY (sws_id)
);

INSERT INTO sws(sws_id, team_name) VALUES
    (1, "베이커리"),
    (2, "라꾸라꾸"),
    (3, "STEADY"),
    (4, "이상청");
```

### b. member 테이블 만들기 
```sql
CREATE TABLE members(
	member_id BIGINT NOT NULL,
    member_name VARCHAR(25) NOT NULL, 
    position VARCHAR(25) NOT NULL,
    email VARCHAR(45) NOT NULL,
    sws_id BIGINT NOT NULL,
    FOREIGN KEY(sws_id) 
    REFERENCES sws(sws_id) ON UPDATE CASCADE
);   

INSERT INTO members(member_id, member_name, position,  email, sws_id) VALUES
	(1, "권지윤", "FRONT/BACK", "ziyun1612@ewhain.net", 2), 
    (2, "권지윤", "FRONT/BACK", "ziyun1612@ewhain.net", 2), 
    (3, "권지윤", "FRONT/BACK", "ziyun1612@ewhain.net" , 2), 
    (4, "권지윤", "FRONT/BACK", "ziyun1612@ewhain.net", 2);

```

### C. MEMBERS 테이블과 SWS 테이블 join하기 
```sql
SELECT  members.member_id, members.member_name, sws.team_name, members.position,  members.email, members.sws_id
FROM members
JOIN sws
ON members.sws_id = sws.sws_id;

```



