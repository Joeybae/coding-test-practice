# coding-test-practice

이용 사이트 : 프로그래머스

1. SELECT 최댓값, 최솟값, 합계 구하기, https://programmers.co.kr/learn/courses/30/lessons/59415

    - 정답 (최댓값)
    
    1) SELECT MAX(DATETIME) from ANIMAL_INS;
    
    2) SELECT DATETIME from ANIMAL_INS order by DATETIME DESC limit 1;
    
    - 정답 (최솟값)
    
    1) SELECT MIN(DATETIME) from ANIMAL_INS;
    
    2) SELECT DATETIME from ANIMAL_INS order by DATETIME ASC limit 1;
    
    - 정답 (합계)
    
    1) SELECT count(DATETIME) from ANIMAL_INS;
    
    - 중복제거
    
    1) SELECT count(DISTINCT NAME) from ANIMAL_INS
    
2. 모든 레코드 조회, https://programmers.co.kr/learn/courses/30/lessons/59034

    - 정답
    
    1) SELECT * from ANIMAL_INS order by ANIMAL_ID ASC;
