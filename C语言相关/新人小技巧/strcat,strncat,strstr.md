在C语言中，`strcat`、`strncat` 和 `strstr` 是处理字符串的常用函数，它们定义在 `<string.h>` 头文件中。下面是这些函数的介绍和使用示例：

1. `strcat` 函数：
   - **功能**：将两个字符串连接起来。`strcat` 函数将 `src` 字符串追加到 `dest` 字符串的末尾，并以空字符 `\0` 结尾。
   - **原型**：`char *strcat(char *dest, const char *src);`
   - **注意**：`dest` 必须有足够的空间来容纳连接后的字符串，否则会导致缓冲区溢出。

   示例代码：
   ```c
   #include <stdio.h>
   #include <string.h>

   int main() {
       char dest[50] = "Hello, ";
       char src[] = "World!";
       
       strcat(dest, src);
       printf("%s\n", dest); // 输出: Hello, World!
       
       return 0;
   }
   ```

2. `strncat` 函数：
   - **功能**：`strncat` 函数将 `src` 字符串的一部分追加到 `dest` 字符串的末尾，最多追加 `n` 个字符。如果 `src` 的长度小于 `n`，则追加整个 `src` 字符串。
   - **原型**：`char *strncat(char *dest, const char *src, size_t n);`
   - **注意**：和 `strcat` 一样，`dest` 必须有足够的空间来容纳连接后的字符串。

   示例代码：
   ```c
   #include <stdio.h>
   #include <string.h>

   int main() {
       char dest[50] = "Hello, ";
       char src[] = "World! This is a test.";
       
       strncat(dest, src, 5); // 只追加 "World!" 到 dest
       printf("%s\n", dest); // 输出: Hello, World!
       
       return 0;
   }
   ```

3. `strstr` 函数：
   - **功能**：`strstr` 函数用于在一个字符串中查找第一次出现的另一个字符串，并返回第一次出现的位置的指针。如果没有找到，则返回 `NULL`。
   - **原型**：`char *strstr(const char *haystack, const char *needle);`

   示例代码：
   ```c
   #include <stdio.h>
   #include <string.h>

   int main() {
       char haystack[] = "Hello, World! Welcome to the world of C programming.";
       char needle[] = "World";
       
       char *found = strstr(haystack, needle);
       if (found) {
           printf("Found '%s' in '%s'\n", needle, haystack);
       } else {
           printf("'%s' not found in '%s'\n", needle, haystack);
       }
       
       return 0;
   }
   ```

在使用这些函数时，特别要注意内存管理，确保目标字符串有足够的空间来存储连接后的字符串，以避免缓冲区溢出的安全问题。在实际编程中，可以考虑使用更安全的函数版本，如 `strcat_s`、`strncat_s` 等，这些函数在一些编译器中提供了对缓冲区溢出的保护。
