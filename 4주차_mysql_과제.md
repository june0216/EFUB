### 4주차 과제 
# (1) 학사 정보 관리 ERD
<img width="383" alt="20220411_131100" src="https://user-images.githubusercontent.com/76603301/162665394-caa0cf53-b687-47e4-88c3-5ace650fe8bf.png">

# (2) mysql 실습

a. sws 테이블 생성하기 
'''sql
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
'''
