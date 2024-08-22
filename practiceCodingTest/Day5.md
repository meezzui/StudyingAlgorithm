### 문제1🧐
문자열 str이 주어집니다.
문자열을 시계방향으로 90도 돌려서 아래 입출력 예와 같이 출력하는 코드를 작성해 보세요.

입출력 예
입력
`abcde`  
출력
`
a
b
c
d
e
`(세로로 출력)

---

### 내가 푼 풀이📝
- 입력된 문자열을 알파벳 단위로 쪼갠 것이 담긴 배열을 만들어준다.
- for문을 이용하여 해당 배열의 요소들을 출력해준다.
```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        String[] arr = a.split("");
       
        for(int i=0; i < arr.length; i++){
            System.out.println(arr[i]);
        }
    }
}
```

### 다른 풀이🌈
- 향상된 for문을 사용.
- `toCharArray()` 사용. `toCharArray()`는 문자열을 문자(char) 배열로 변환한다.
- 예를 들어, "hello"라는 문자열이 주어지면, 이를 ['h', 'e', 'l', 'l', 'o']라는 문자 배열로 변환한다.
```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        for (char ch : a.toCharArray())
            System.out.println(ch);
    }
}
```


### 문제2🧐
자연수 n이 입력으로 주어졌을 때 만약 n이 짝수이면 "n is even"을, 홀수이면 "n is odd"를 출력하는 코드를 작성해 보세요.  

[예시]  
입력: 100  
출력: 100 is even  

입력: 1    
출력: 1 is odd

---

### 내가 푼 풀이📝
- if문을 사용하여 짝수와 홀수일 경우로 분기를 쳐줬다.
```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        
        if(n % 2 == 0){
            System.out.println(n + " is even");
        }
        else System.out.println(n + " is odd");
    }
}
```

### 다른 풀이🌈
- if문이 아닌 삼항연산자를 사용하여 더 간단하게 풀어낼 수 있다.
```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

        System.out.print(n + " is "+(n % 2 == 0 ? "even" : "odd"));
    }
}
```
















