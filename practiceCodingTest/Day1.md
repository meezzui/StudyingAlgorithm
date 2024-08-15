### 문제🧐
#### 정수로 이루어진 배열이 주어졌을 때, 배열 내에서 중복되지 않는 정수의 개수를 찾는 함수를 구현하세요.  
#### 예를 들어, [1, 2, 2, 3, 4, 4, 5]가 주어졌을 때, 중복되지 않는 정수는 1, 3, 5이므로 함수는 3을 반환해야 합니다.
---
### 풀이📝

```ruby
public static int countUniqueElements(int[] arr) {

        Map<Integer, Integer> frequencyMap = new HashMap<>();
        int uniqueCount = 0;

        // 배열 요소들의 빈도수를 세기
        for (int num : arr) {
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }

        // 빈도수가 1인 요소들의 개수 세기
        for (int frequency : frequencyMap.values()) {
            if (frequency == 1) {
                uniqueCount++;
            }
        }

        return uniqueCount;
    }

    public static void main(String[] args) {
        int[] arr = {2,3,3,1,1};
        System.out.println("중복되지 않은 정수의 개수:" + countUniqueElements(arr)); // 출력: 1
    }
```
