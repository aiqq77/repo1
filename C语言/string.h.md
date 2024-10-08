`<string.h>`头文件中包含了许多用于字符串操作的函数，以下是一些常见函数及其作用：

### 1. `strcpy`
- 作用：把源字符串复制到目标字符串中。
- 示例：
```c
char src[] = "Hello";
char dest[6];
strcpy(dest, src); // dest 现在为 "Hello"
```

### 2. `strncpy`
- 作用：把源字符串的一部分复制到目标字符串中。
- 示例：
```c
char src[] = "Hello World";
char dest[6];
strncpy(dest, src, 5); // dest 现在为 "Hello"
```

### 3. `strcat`
- 作用：将源字符串连接到目标字符串的末尾。
- 示例：
```c
char str1[] = "Hello";
char str2[] = " World";
strcat(str1, str2); // str1 现在为 "Hello World"
```

### 4. `strncat`
- 作用：将源字符串的一部分连接到目标字符串的末尾。
- 示例：
```c
char str1[] = "Hello";
char str2[] = " World";
strncat(str1, str2, 3); // str1 现在为 "Hello Wor"
```

### 5. `strcmp`
- 作用：比较两个字符串。如果两个字符串相等，返回 0；如果第一个字符串小于第二个字符串，返回负数；如果第一个字符串大于第二个字符串，返回正数。
- 示例：
```c
char str1[] = "apple";
char str2[] = "banana";
int result = strcmp(str1, str2); // result 为负数
```

### 6. `strncmp`
- 作用：比较两个字符串的前 n 个字符。
- 示例：
```c
char str1[] = "apple";
char str2[] = "applesauce";
int result = strncmp(str1, str2, 5); // result 为 0
```

### 7. `strlen`
- 作用：计算字符串的长度，不包括字符串结束符'\0'。
- 示例：
```c
char str[] = "Hello";
int length = strlen(str); // length 为 5
```

### 8. `strchr`
- 作用：在一个字符串中查找指定字符第一次出现的位置。
- 示例：
```c
char str[] = "Hello World";
char *result = strchr(str, 'o'); // result 指向字符串中第一个 'o' 的位置
```

### 9. `strrchr`
- 作用：在一个字符串中查找指定字符最后一次出现的位置。
- 示例：
```c
char str[] = "Hello World";
char *result = strrchr(str, 'o'); // result 指向字符串中最后一个 'o' 的位置
```

### 10. `strstr`
- 作用：在一个字符串中查找另一个字符串第一次出现的位置。
- 示例：
```c
char str1[] = "Hello World";
char str2[] = "World";
char *result = strstr(str1, str2); // result 指向 "World" 在 str1 中的位置
```