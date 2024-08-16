### 문제🧐
영어 알파벳으로 이루어진 문자열 str이 주어집니다.  
각 알파벳을 대문자는 소문자로 소문자는 대문자로 변환해서 출력하는 코드를 작성해 보세요.

[제한사항]  
1 ≤ str의 길이 ≤ 20  
str은 알파벳으로 이루어진 문자열입니다.  

입력: aBcDeFg  
출력: AbCdEfG  

### 내가 작성한 풀이📝
- `if(a.length() > 20 || !a.matches("^[a-zA-Z]*$")){}` 이 로직으로 제한사항을 벗어날 경우 프로그램이 종료되게 구현
- `toCharArray()` 함수를 사용하여 배열에 한 글자씩 담아서 알파벳을 비교  
☀️ `toCharArray()`: String 문자열을 char형 배열로 바꿔서 반환해주는 메서드
- `toLowerCase()`, `toUpperCase()` 함수를 사용하여 대소문자로 바꿔줌

```ruby
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        
        if(a.length() > 20 || !a.matches("^[a-zA-Z]*$")){
            System.out.println("글자수는 최대 20까지이며 문자열은 알파벳만 입력 가능합니다. \n 프로그램을 종료합니다.");
            return;
        }
        
       char[] ch = a.toCharArray();
        for(char c : ch){
            if(Character.isUpperCase(c))
            {
                c = Character.toLowerCase(c);
            }
            else
            {
                c = Character.toUpperCase(c);
            }
        System.out.print(c);
        }
    }
}
```
