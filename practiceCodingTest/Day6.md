### 문제🧐
얀에서는 매년 달리기 경주가 열립니다. 해설진들은 선수들이 자기 바로 앞의 선수를 추월할 때 추월한 선수의 이름을 부릅니다. 예를 들어 1등부터 3등까지 "mumu", "soe", "poe" 선수들이 순서대로 달리고 있을 때, 해설진이 "soe"선수를 불렀다면 2등인 "soe" 선수가 1등인 "mumu" 선수를 추월했다는 것입니다. 즉 "soe" 선수가 1등, "mumu" 선수가 2등으로 바뀝니다.

선수들의 이름이 1등부터 현재 등수 순서대로 담긴 문자열 배열 players와 해설진이 부른 이름을 담은 문자열 배열 callings가 매개변수로 주어질 때, 경주가 끝났을 때 선수들의 이름을 1등부터 등수 순서대로 배열에 담아 return 하는 solution 함수를 완성해주세요.

입출력 예시  
```
players		
["mumu", "soe", "poe", "kai", "mine"]

callings
["kai", "kai", "mine", "mine"]	

result
["mumu", "kai", "mine", "soe", "poe"]

설명
4등인 "kai" 선수가 2번 추월하여 2등이 되고 앞서 3등, 2등인 "poe", "soe" 선수는 4등, 3등이 됩니다.
5등인 "mine" 선수가 2번 추월하여 4등, 3등인 "poe", "soe" 선수가 5등, 4등이 되고 경주가 끝납니다.
1등부터 배열에 담으면 ["mumu", "kai", "mine", "soe", "poe"]이 됩니다.
```

### 문제 풀이 전략🌈
- 이 문제는 players 배열에 담긴 선수들의 순서를 callings 배열에 따라 조정하는 것이다.
- 현재 선수들의 순서 관리 -> 선수들의 현재 순서를 관리하기 위해 HashMap을 사용하여 선수 이름을 키로, 해당 선수의 현재 인덱스를 값으로 저장
- 추월 처리 -> callings 배열을 순회하며, 추월이 발생할 때마다 해당 선수와 바로 앞 선수의 위치를 교환하고, HashMap을 업데이트 함
- 최종 결과 반환 -> 모든 추월이 끝난 후, 최종 players 배열을 반환

### 문제 풀이📝
```ruby
import java.util.HashMap;

public class Solution {
    public String[] solution(String[] players, String[] callings) {

        // 선수 이름과 현재 인덱스를 저장하는 HashMap
        HashMap<String, Integer> indexMap = new HashMap<>();

        // 초기 선수 배열의 순서를 HashMap에 저장
        for (int i = 0; i < players.length; i++) {
            indexMap.put(players[i], i);
        }

        // callings 배열을 순회하며 추월 발생 시 처리
        for (String calling : callings) {
            // 호출된 선수의 현재 인덱스
            int idx = indexMap.get(calling);

            // 만약 idx가 0보다 크면, 추월할 수 있는 상태임을 의미
            if (idx > 0) {
                // 현재 선수와 바로 앞 선수의 위치를 교환
                String temp = players[idx - 1];
                players[idx - 1] = players[idx];
                players[idx] = temp;

                // 변경된 위치를 HashMap에 업데이트
                // 교환이 이루어진 후, indexMap을 업데이트하여 두 플레이어의 새로운 인덱스를 저장
                indexMap.put(players[idx], idx);
                indexMap.put(players[idx - 1], idx - 1);
            }
        }

        // 최종 변경된 선수 배열을 반환
        return players;
    }
}
```
