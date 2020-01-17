# coding-test-practice

이용 사이트 : 프로그래머스

------------------------

2020년 1월 17일 금요일

1. 탑, https://programmers.co.kr/learn/courses/30/lessons/42588

    - 입력값 / 출력값
        
            heights	        return
            [6,9,5,7,4]	    [0,0,2,2,4]
            [3,9,9,3,5,7,2]	[0,0,0,3,3,3,6]
            [1,5,3,6,7,6,5]	[0,0,2,0,0,5,6]
            
     - 정답
     
            function solution(heights) {
            var answer = [];
            var len = heights.length-1;
            console.log(heights)
            var i,j;
            for(i = len;i>=0;i--){
                answer[i] = 0;
                for(j=i-1;j>=0;j--){
                    if(heights[i] < heights[j]){
                        answer[i] = j+1;
                        break;
                    }
                }
            }
            return answer;
            }

------------------------

2020년 1월 16일 목요일

1. SELECT 최댓값, 최솟값, 합계 구하기, https://programmers.co.kr/learn/courses/30/lessons/59415

    - 정답 (최댓값)
    
        1) SELECT MAX(DATETIME) from ANIMAL_INS;
    
        2) SELECT DATETIME from ANIMAL_INS order by DATETIME DESC limit 1;
    
    - 정답 (최솟값)
    
        1) SELECT MIN(DATETIME) from ANIMAL_INS;
    
        2) SELECT DATETIME from ANIMAL_INS order by DATETIME ASC limit 1;
    
    - 정답 (합계)
    
        - SELECT count(DATETIME) from ANIMAL_INS;
    
    - 중복제거
    
        - SELECT count(DISTINCT NAME) from ANIMAL_INS
    
2. 레코드 조회, https://programmers.co.kr/learn/courses/30/lessons/59034

    - 정답 (모든 레코드 조회)
    
        - SELECT * from ANIMAL_INS order by ANIMAL_ID ASC;
    
    - 정답 (역순)
    
        - select name, datetime from animal_ins order by animal_id desc;
    
    - 정답 (아픈동물찾기)
    
        - SELECT animal_id, name from animal_ins where INTAKE_CONDITION = "Sick";
    
    - 정답 (어린동물찾기)
    
        - SELECT animal_id, name from animal_ins where INTAKE_CONDITION not in ("Aged");
    
    - 정답 (동물의 아이디와 이름)
    
        - SELECT animal_id, name from animal_ins order by animal_id asc;
    
    - 정답 (여러기준으로 정렬하기)
    
        - SELECT animal_id, name, datetime from animal_ins order by name asc, datetime desc
    
    - 정답 (상위 n개 레코드)
    
        - SELECT name from animal_ins order by datetime asc limit 1;
