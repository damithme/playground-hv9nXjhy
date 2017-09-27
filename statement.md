# Introduction
Learn how to reverse a String using Stack. In this example takes in an array based Stack.

[Stack – Data Structure](https://tech.io/playgrounds/5407338183ed1752c1ee224322874a6c5256/stack-data-structure)  – Array-based and Linked list based implementation.

The followings are the steps to reversing a String using Stack.

1. **String** to **Char[]**.
2. Create a Stack.
3. Push all characters, one by one.
4. Then Pop all characters, one by one and put into the char[].
5. Finally, convert to the String.

```java
public static String reverse(String str) {
        char[] charArr = str.toCharArray();
        int size = charArr.length;
        Stack stack = new Stack(size);

        int i;
        for(i = 0; i < size; ++i) {
            stack.push(charArr[i]);
        }

        for(i = 0; i < size; ++i) {
            charArr[i] = stack.pop();
        }

        return String.valueOf(charArr);
}
```

**Time complexity – O(n)**

**Space complexity – O(n)**

# Complete Example
```java runnable
class Stack {
    private int top;
    private int capacity;
    private char[] array;

    public Stack(int capacity) {
        this.capacity = capacity;
        this.array = new char[capacity];
        this.top = -1;
    }

    public boolean isFull() {
        return this.top == this.capacity - 1;
    }

    public boolean isEmpty() {
        return this.top == -1;
    }

    public void push(char value) {
        if(!this.isFull()) {
            this.array[++this.top] = value;
        }
    }

    public char pop() {
        return this.isEmpty()?'\u0000':this.array[this.top--];
    }

    public static String reverse(String str) {
        char[] charArr = str.toCharArray();
        int size = charArr.length;
        Stack stack = new Stack(size);

        int i;
        for(i = 0; i < size; ++i) {
            stack.push(charArr[i]);
        }

        for(i = 0; i < size; ++i) {
            charArr[i] = stack.pop();
        }

        return String.valueOf(charArr);
    }


}
public class Main {
  public static void main(String[] args) {
      String str = "MYDEVGEEK";
      System.out.println(Stack.reverse(str));
  }
}
```

Original post : - http://mydevgeek.com/stack-reverse-string-using-stack/
