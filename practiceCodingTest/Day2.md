### 문제🧐
문자열 str과 정수 n이 주어집니다.  
str이 n번 반복된 문자열을 만들어 출력하는 코드를 작성해 보세요.  

입력: string 5  
출력: stringstringstringstringstring  

[제한 사항]  
1 ≤ str의 길이 ≤ 10  
1 ≤ n ≤ 5
### 내가 작성한 풀이📝
- 제한 사항에 따라서 입력 받을 수 있는 문자열의 길이랑 정수의 범위가 해당 범위를 넘어갈 시 프로그램이 종료되게 로직을 구현.
- `Exception` 최상위 예외 클래스가 아닌 `IllegalArgumentException` 예외 클래스를 사용하여 예외 상황을 더 정확히 처리.
- `IllegalArgumentException` : 메서드에 전달된 인수가 부적절할 때 사용됨. 즉, 문자열 길이가 허용된 범위를 벗어났을 때 사용.
- for문 대신 repeat() 함수를 써서 코드를 간결하게 해줌.

```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.next();
        try{
            if(str.length() <=10)
        }
        catch(IllegalArgumentException e){
            System.out.println("문자열의 길이는 최대 10자까지 가능합니다.");
            return; // 프로그램 종료
        }
        
        int n = sc.nextInt();
        
        if(n > 5){
            System.out.println("정수는 5까지만 가능합니다.");
            return; // 프로그램 종료
        }
        
        System.out.println(str.repeat(n));
    }
}
```
