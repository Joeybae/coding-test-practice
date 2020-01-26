# coding-test-practice

이용 사이트 : 프로그래머스

----------------------------

2020 1월 25일 토요일

- 설날 

----------------------------

2020 1월 20일 월요일

1. K번째 수, https://programmers.co.kr/learn/courses/30/lessons/42748 (2번째 test 틀림, 정확률 85.7%), 틀린 이유는 sort부분으로 function 추가로 수정.

        function solution(array, commands) {
            var answer = [];
            for(var x=0; x < commands.length; x++){
                var i = commands[x][0];
                var j = commands[x][1];
                var k = commands[x][2];
                var temp = array.slice(i-1, j).sort(function(a,b){
                    return a-b;
                });
                answer.push(temp[k-1]);
            }
            return answer;
        }

----------------------------

2020 1월 19일 일요일

- 이전 문제 확인 및 재공부

----------------------------

2020 1월 18일 토요일

1.모의고사, https://programmers.co.kr/learn/courses/30/lessons/42840?language=javascript (실패)

    function solution(answers) {
        var answer = [];
        const man1 = [1, 2, 3, 4, 5];
        const man2 = [2, 1, 2, 3, 2, 4, 2, 5];
        const man3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5];
        let count = [0, 0, 0];

        for(let i = 0; i < answers.length; i++) {
            if(answers[i] == man1[i % man1.length]) count[0]++;
            if(answers[i] == man2[i % man2.length]) count[1]++;
            if(answers[i] == man3[i % man3.length]) count[2]++;
        }

        const max = Math.max(count[0], count[1], count[2]);
        for(let i = 0; i < count.length; i++) {
            if(max == count[i]) answer.push(i + 1);
        }

        return answer;
    }

----------------------------

2020년 1월 17일 금요일

1. 탑, https://programmers.co.kr/learn/courses/30/lessons/42588 (실패)

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
            
 2. 완주하지 못한 선수, https://programmers.co.kr/learn/courses/30/lessons/42576 (실패)
 
    - 입력값 / 출력값
    
            participant	                            completion	                        return
            [leo, kiki, eden]	                    [eden, kiki]	                    leo
            [marina, josipa, nikola, vinko, filipa]	[josipa, filipa, marina, nikola]	vinko
            [mislav, stanko, mislav, ana]	        [stanko, ana, mislav]	            mislav
    
    - 정답
    
            function solution(participant, completion) {
                participant.sort()
                completion.sort()
                for(let i=0; i<participant.length; i++){
                    if(participant[i]!=completion[i]){
                      return participant[i]
                      break;
                    }
                }
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
