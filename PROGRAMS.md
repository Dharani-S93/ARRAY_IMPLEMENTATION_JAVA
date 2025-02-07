

### 1. Sum of Elements in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];
        int sum = 0;

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
            sum += a[i];
        }

        System.out.println(sum);
    }
}
```
**Input:**  
```
5  
1 2 3 4 5  
```
**Output:**  
```
15
```

---  
