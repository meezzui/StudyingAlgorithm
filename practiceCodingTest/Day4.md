### 문제1🧐

특수문자 출력하기   
주어진 특수 문자: `!@#$%^&*(\'"<>?:;`
---

### 문제 풀이📝
- 자바는 백슬래시( \ ) 와 따옴표 ( '' ) ( "" ) 는 문자 그대로 출력되지 않는다.
- 왜냐하면 출력문은 `System.out.print("hello");` 처럼 쌍따옴표 안의 내용을 출력하기 때문에, 중간에 " 가 나오면 거기서 내용이 끝나는 거라고 인식하기 때문이다.
- 그래서 문자로 따옴표를 쓸 때는 앞에 백슬래시를 붙여주면 된다. -> `\"` 혹은 `\'`

```code
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        System.out.println("!@#$%^&*(\\'\"<>?:;");
    }
}
```

### 문제2🧐
덧셈식 출력하기  
`a+b=c`  


[제한사항]
`1 ≤ a, b ≤ 100`  


입력 값: 4 5  
출력 값: 4 + 5 = 9
---

### 내 풀이📝
- 정수 a,b 값의 제한 사항과 맞지 않을 시 프로그램 종료되게 예외처리
- 정수 값 하나를 더 선언해서 더한 값을 저장해줌

```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        
        if(a < 1 || b > 100){
            return;
        }
        
        int c = a + b;

        System.out.println(a + " + " + b + " = " + c);
    }
}
```

### 다른 풀이☀️
- 출력할 덧셈식 형태를 만들어주고 헤당 깂에 정수가 할당될 수 있게 서식 문자열 사용
  
```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();

        System.out.printf("%d + %d = %d",a,b,a+b);
    }
}
```

### 문제3🧐
두 개의 문자열 str1, str2가 공백으로 구분되어 입력으로 주어집니다.
입출력 예와 같이 str1과 str2을 이어서 출력하는 코드를 작성해 보세요.

[제한사항]
`1 ≤ str1, str2의 길이 ≤ 10`

### 내가 푼 풀이📝
- 문자열이 제한사항 범위를 넘어서 입력되면 프로그램이 종료되게 구현 
- `concat()` 함수를 사용하여 문자열을 붙여서 출력
  
```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        String b = sc.next();

        if(a.length() < 1 || b.length() > 10) return;

        System.out.println(a.concat(b));
    }
}
```
