# 字符串系列

## 1.回文字符串

> 忽略大小写，和特殊字符

```java
package com.jaiken.leetcode.string;

import org.junit.Test;

public class ValidPalindrome {
    public boolean checkPdString(String input) {
        if (input == null || input.length() == 0) {
            return true;
        }
        StringBuilder sb = new StringBuilder();
        for (char c : input.toLowerCase().toCharArray()) {
            if (c >= 'A' && c <= 'z') {sudo dpkg --purge  code sudo dpkg --purge  code 
                sb.append(c);
            }
        }
        if (sb.length() == 0) {
            return true;
        }
        String leftToRight = sb.toString();
        String rightToLst = sb.reverse().toString();
        return leftToRight.equals(rightToLst);
    }

    public boolean checkPdString2(String input) {
        if (input == null || input.length() == 0) {
            return true;
        }
        int left = 0;
        int right = input.length() - 1;
        String temp = input.toLowerCase();
        while (left < right) {
            char leftChar = temp.charAt(left);
            char rightChar = temp.charAt(right);
            if (leftChar > 'z' || leftChar < 'a') {
                left++;
                continue;
            }
            if (rightChar > 'z' || rightChar < 'a') {
                right--;
                continue;
            }
            if (leftChar != rightChar) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }

    @Test
    public void test() {
        String input = "race a car.";
        System.out.println(checkPdString2(input));
        String input2 = "abBbba";
        System.out.println(checkPdString2(input2));
    }
}
```