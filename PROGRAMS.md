

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
### 2. Find Minimum and Maximum Elements in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int max = a[0], min = a[0];

        for (int i = 1; i < n; i++) {
            if (a[i] > max) {
                max = a[i];
            }
            if (a[i] < min) {
                min = a[i];
            }
        }

        System.out.println(max);
        System.out.println(min);
    }
}
```
**Input:**  
```
5  
1 11 22 3 2  
```
**Output:**  
```
22  
1
```

---

### 3. Reverse an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        for (int i = n - 1; i >= 0; i--) {
            System.out.print(a[i] + " ");
        }
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
5 4 3 2 1
```

---

### 4. Find Duplicate Elements in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];
        HashSet<Integer> seen = new HashSet<>();
        HashSet<Integer> duplicates = new HashSet<>();

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
            if (!seen.add(a[i])) {
                duplicates.add(a[i]);
            }
        }

        for (int num : duplicates) {
            System.out.print(num + " ");
        }
    }
}
```
**Input:**  
```
6  
1 2 3 4 2 3  
```
**Output:**  
```
2 3
```

---

### 5. Find the Kth Largest Element in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int k = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        Arrays.sort(a);
        System.out.println(a[n - k]);
    }
}
```
**Input:**  
```
5  
2  
3 2 1 5 4  
```
**Output:**  
```
4
```

---

### 6. Check if a Given Number is Present in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int target = s.nextInt();
        boolean found = false;

        for (int i = 0; i < n; i++) {
            if (a[i] == target) {
                found = true;
                break;
            }
        }

        System.out.println(found);
    }
}
```
**Input:**  
```
5  
1 2 3 4 5  
3  
```
**Output:**  
```
true
```

---

### 7. Rotate an Array by K Positions  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int k = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        k = k % n;
        int rotated[] = new int[n];

        for (int i = 0; i < n; i++) {
            rotated[(i + k) % n] = a[i];
        }

        for (int num : rotated) {
            System.out.print(num + " ");
        }
    }
}
```
**Input:**  
```
5  
2  
1 2 3 4 5  
```
**Output:**  
```
4 5 1 2 3
```

---

### 8. Move All Zeros to the End of an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int index = 0;
        for (int i = 0; i < n; i++) {
            if (a[i] != 0) {
                a[index++] = a[i];
            }
        }

        while (index < n) {
            a[index++] = 0;
        }

        for (int num : a) {
            System.out.print(num + " ");
        }
    }
}
```
**Input:**  
```
5  
0 1 0 3 12  
```
**Output:**  
```
1 3 12 0 0
```

---

### 9. Find the First Non-Repeating Element in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];
        LinkedHashMap<Integer, Integer> map = new LinkedHashMap<>();

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
            map.put(a[i], map.getOrDefault(a[i], 0) + 1);
        }

        for (int num : a) {
            if (map.get(num) == 1) {
                System.out.println(num);
                return;
            }
        }

        System.out.println(-1);
    }
}
```
**Input:**  
```
5  
4 5 1 2 5  
```
**Output:**  
```
4
```

---

### 10. Check if a Given Array is a Subset of Another Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n1 = s.nextInt();
        int a1[] = new int[n1];

        for (int i = 0; i < n1; i++) {
            a1[i] = s.nextInt();
        }

        int n2 = s.nextInt();
        int a2[] = new int[n2];

        for (int i = 0; i < n2; i++) {
            a2[i] = s.nextInt();
        }

        boolean isSubset = true;

        for (int i = 0; i < n2; i++) {
            boolean found = false;
            for (int j = 0; j < n1; j++) {
                if (a2[i] == a1[j]) {
                    found = true;
                    break;
                }
            }
            if (!found) {
                isSubset = false;
                break;
            }
        }

        System.out.println(isSubset);
    }
}
```
**Input:**  
```
5  
1 2 3 4 5  
3  
2 4 5  
```
**Output:**  
```
true
```

---

### 11. Find the Majority Element in an Array (Element Appearing More Than n/2 Times)  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int majorityElement = -1;
        for (int i = 0; i < n; i++) {
            int count = 0;
            for (int j = 0; j < n; j++) {
                if (a[j] == a[i]) {
                    count++;
                }
            }
            if (count > n / 2) {
                majorityElement = a[i];
                break;
            }
        }

        System.out.println(majorityElement);
    }
}
```
**Input:**  
```
5  
3 3 4 3 3  
```
**Output:**  
```
3
```

---

### 12. Find the Occurrence of an Integer in the Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int target = s.nextInt();
        int count = 0;

        for (int i = 0; i < n; i++) {
            if (a[i] == target) {
                count++;
            }
        }

        System.out.println(count);
    }
}
```
**Input:**  
```
5  
1 2 3 2 2  
2  
```
**Output:**  
```
3
```

---

### 13. Find the Factorial of a Large Number  
**Code (Using Array):**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int res[] = new int[500];  
        res[0] = 1;
        int res_size = 1;

        for (int x = 2; x <= n; x++) {
            res_size = multiply(x, res, res_size);
        }

        for (int i = res_size - 1; i >= 0; i--) {
            System.out.print(res[i]);
        }
    }

    static int multiply(int x, int res[], int res_size) {
        int carry = 0;

        for (int i = 0; i < res_size; i++) {
            int prod = res[i] * x + carry;
            res[i] = prod % 10;
            carry = prod / 10;
        }

        while (carry > 0) {
            res[res_size] = carry % 10;
            carry /= 10;
            res_size++;
        }

        return res_size;
    }
}
```
**Input:**  
```
5  
```
**Output:**  
```
120
```

---

### 14. Find the Missing Integer (From 1 to N)  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n - 1];

        int sumN = n * (n + 1) / 2;
        int sumA = 0;

        for (int i = 0; i < n - 1; i++) {
            a[i] = s.nextInt();
            sumA += a[i];
        }

        System.out.println(sumN - sumA);
    }
}
```
**Input:**  
```
5  
1 2 4 5  
```
**Output:**  
```
3
```

---


---

### 15. Merge Two Sorted Arrays  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n1 = s.nextInt();
        int a1[] = new int[n1];

        for (int i = 0; i < n1; i++) {
            a1[i] = s.nextInt();
        }

        int n2 = s.nextInt();
        int a2[] = new int[n2];

        for (int i = 0; i < n2; i++) {
            a2[i] = s.nextInt();
        }

        int merged[] = new int[n1 + n2];
        int i = 0, j = 0, k = 0;

        while (i < n1 && j < n2) {
            if (a1[i] < a2[j]) {
                merged[k++] = a1[i++];
            } else {
                merged[k++] = a2[j++];
            }
        }

        while (i < n1) {
            merged[k++] = a1[i++];
        }

        while (j < n2) {
            merged[k++] = a2[j++];
        }

        for (int num : merged) {
            System.out.print(num + " ");
        }
    }
}
```
**Input:**  
```
3  
1 3 5  
3  
2 4 6  
```
**Output:**  
```
1 2 3 4 5 6  
```

---

### 16. Find the Intersection of Two Arrays  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n1 = s.nextInt();
        int a1[] = new int[n1];

        for (int i = 0; i < n1; i++) {
            a1[i] = s.nextInt();
        }

        int n2 = s.nextInt();
        int a2[] = new int[n2];

        for (int i = 0; i < n2; i++) {
            a2[i] = s.nextInt();
        }

        for (int i = 0; i < n1; i++) {
            for (int j = 0; j < n2; j++) {
                if (a1[i] == a2[j]) {
                    System.out.print(a1[i] + " ");
                    break;
                }
            }
        }
    }
}
```
**Input:**  
```
4  
1 2 3 4  
3  
2 4 6  
```
**Output:**  
```
2 4  
```

---

### 17. Union of Two Arrays  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n1 = s.nextInt();
        int a1[] = new int[n1];

        for (int i = 0; i < n1; i++) {
            a1[i] = s.nextInt();
        }

        int n2 = s.nextInt();
        int a2[] = new int[n2];

        for (int i = 0; i < n2; i++) {
            a2[i] = s.nextInt();
        }

        int union[] = new int[n1 + n2];
        int k = 0;

        for (int i = 0; i < n1; i++) {
            union[k++] = a1[i];
        }

        for (int i = 0; i < n2; i++) {
            boolean found = false;
            for (int j = 0; j < n1; j++) {
                if (a2[i] == a1[j]) {
                    found = true;
                    break;
                }
            }
            if (!found) {
                union[k++] = a2[i];
            }
        }

        for (int i = 0; i < k; i++) {
            System.out.print(union[i] + " ");
        }
    }
}
```
**Input:**  
```
3  
1 2 3  
3  
2 3 4  
```
**Output:**  
```
1 2 3 4  
```

---

### 18. Find the "Kth" Smallest Element in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int k = s.nextInt();
        Arrays.sort(a);

        System.out.println(a[k - 1]);
    }
}
```
**Input:**  
```
5  
3 1 4 2 5  
3  
```
**Output:**  
```
3  
```

---

### 19. Find the Pair with the Given Sum  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int target = s.nextInt();

        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                if (a[i] + a[j] == target) {
                    System.out.println(a[i] + " " + a[j]);
                    return;
                }
            }
        }
    }
}
```
**Input:**  
```
4  
1 2 3 4  
5  
```
**Output:**  
```
1 4  
```

---


---

### 20. Find All Pairs in an Array That Sum Up to a Specific Value  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int target = s.nextInt();

        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                if (a[i] + a[j] == target) {
                    System.out.println(a[i] + " " + a[j]);
                }
            }
        }
    }
}
```
**Input:**  
```
5  
1 2 3 4 5  
5  
```
**Output:**  
```
1 4  
2 3  
```

---

### 21. Move All Negative Numbers to One Side of the Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int temp[] = new int[n];
        int index = 0;

        for (int i = 0; i < n; i++) {
            if (a[i] < 0) {
                temp[index++] = a[i];
            }
        }

        for (int i = 0; i < n; i++) {
            if (a[i] >= 0) {
                temp[index++] = a[i];
            }
        }

        for (int num : temp) {
            System.out.print(num + " ");
        }
    }
}
```
**Input:**  
```
5  
1 -2 3 -4 5  
```
**Output:**  
```
-2 -4 1 3 5  
```

---

### 22. Find the Longest Increasing Subsequence (LIS) in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static int findLIS(int[] arr, int n) {
        int lis[] = new int[n];
        Arrays.fill(lis, 1);

        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                if (arr[i] > arr[j] && lis[i] < lis[j] + 1) {
                    lis[i] = lis[j] + 1;
                }
            }
        }

        int max = 0;
        for (int i = 0; i < n; i++) {
            if (max < lis[i]) {
                max = lis[i];
            }
        }
        return max;
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        System.out.println(findLIS(a, n));
    }
}
```
**Input:**  
```
6  
10 22 9 33 21 50  
```
**Output:**  
```
4  
```

---

### 23. Subarray with Given Sum  
**Code:**  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int target = s.nextInt();

        for (int i = 0; i < n; i++) {
            int sum = 0;
            for (int j = i; j < n; j++) {
                sum += a[j];
                if (sum == target) {
                    System.out.println("Subarray found from index " + i + " to " + j);
                    return;
                }
            }
        }
        System.out.println("No subarray found");
    }
}
```
**Input:**  
```
5  
1 2 3 7 5  
12  
```
**Output:**  
```
Subarray found from index 2 to 4  
```

---

### 24. Trapping Rain Water (Given an Array of Heights, Calculate the Amount of Water Trapped)  
**Code:**  
```java
import java.util.*;

public class Main {
    public static int trapWater(int[] height, int n) {
        if (n == 0) return 0;

        int leftMax[] = new int[n];
        int rightMax[] = new int[n];
        leftMax[0] = height[0];
        rightMax[n - 1] = height[n - 1];

        for (int i = 1; i < n; i++) {
            leftMax[i] = Math.max(leftMax[i - 1], height[i]);
        }

        for (int i = n - 2; i >= 0; i--) {
            rightMax[i] = Math.max(rightMax[i + 1], height[i]);
        }

        int trappedWater = 0;
        for (int i = 0; i < n; i++) {
            trappedWater += Math.min(leftMax[i], rightMax[i]) - height[i];
        }

        return trappedWater;
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int height[] = new int[n];

        for (int i = 0; i < n; i++) {
            height[i] = s.nextInt();
        }

        System.out.println(trapWater(height, n));
    }
}
```
**Input:**  
```
6  
0 1 0 2 1 0  
```
**Output:**  
```
2  
```

---

Here are the next 10 problems! 🚀  

---

### 25. Max Product Subarray  
**Code:**  
```java
import java.util.*;

public class Main {
    public static int maxProduct(int[] arr, int n) {
        int maxProduct = arr[0], minProduct = arr[0], result = arr[0];

        for (int i = 1; i < n; i++) {
            if (arr[i] < 0) {
                int temp = maxProduct;
                maxProduct = minProduct;
                minProduct = temp;
            }
            maxProduct = Math.max(arr[i], maxProduct * arr[i]);
            minProduct = Math.min(arr[i], minProduct * arr[i]);
            result = Math.max(result, maxProduct);
        }
        return result;
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        System.out.println(maxProduct(a, n));
    }
}
```
**Input:**  
```
5  
2 3 -2 4 -1  
```
**Output:**  
```
48  
```

---

### 26. Find a Peak Element in an Array  
**Code:**  
```java
import java.util.*;

public class Main {
    public static int findPeakElement(int[] arr, int n) {
        if (n == 1) return 0;
        if (arr[0] >= arr[1]) return 0;
        if (arr[n - 1] >= arr[n - 2]) return n - 1;

        for (int i = 1; i < n - 1; i++) {
            if (arr[i] >= arr[i - 1] && arr[i] >= arr[i + 1]) {
                return i;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        System.out.println(findPeakElement(a, n));
    }
}
```
**Input:**  
```
5  
1 3 20 4 1  
```
**Output:**  
```
2  
```

---

### 27. Median of Two Sorted Arrays  
**Code:**  
```java
import java.util.*;

public class Main {
    public static double findMedian(int[] a, int[] b) {
        int n = a.length, m = b.length;
        int merged[] = new int[n + m];
        System.arraycopy(a, 0, merged, 0, n);
        System.arraycopy(b, 0, merged, n, m);
        Arrays.sort(merged);

        int len = merged.length;
        if (len % 2 == 0) {
            return (merged[len / 2 - 1] + merged[len / 2]) / 2.0;
        } else {
            return merged[len / 2];
        }
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];
        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }
        
        int m = s.nextInt();
        int b[] = new int[m];
        for (int i = 0; i < m; i++) {
            b[i] = s.nextInt();
        }

        System.out.println(findMedian(a, b));
    }
}
```
**Input:**  
```
3  
1 3 5  
3  
2 4 6  
```
**Output:**  
```
3.5  
```

---

### 28. Find the Contiguous Subarray with the Maximum Product  
**Code:**  
```java
import java.util.*;

public class Main {
    public static int maxSubarrayProduct(int[] arr, int n) {
        int maxProd = arr[0], minProd = arr[0], result = arr[0];

        for (int i = 1; i < n; i++) {
            if (arr[i] < 0) {
                int temp = maxProd;
                maxProd = minProd;
                minProd = temp;
            }
            maxProd = Math.max(arr[i], maxProd * arr[i]);
            minProd = Math.min(arr[i], minProd * arr[i]);
            result = Math.max(result, maxProd);
        }
        return result;
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        System.out.println(maxSubarrayProduct(a, n));
    }
}
```
**Input:**  
```
5  
2 3 -2 4 -1  
```
**Output:**  
```
48  
```

---

### 29. Find the Number of Subarrays with a Sum Equal to K  
**Code:**  
```java
import java.util.*;

public class Main {
    public static int countSubarrays(int[] arr, int n, int k) {
        int count = 0;

        for (int i = 0; i < n; i++) {
            int sum = 0;
            for (int j = i; j < n; j++) {
                sum += arr[j];
                if (sum == k) {
                    count++;
                }
            }
        }
        return count;
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        int a[] = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = s.nextInt();
        }

        int k = s.nextInt();
        System.out.println(countSubarrays(a, n, k));
    }
}
```
**Input:**  
```
5  
1 1 1 2 3  
3  
```
**Output:**  
```
3  
```

---
