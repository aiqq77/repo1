`<stdio.h>`是 C 语言中非常重要的头文件，包含了许多用于标准输入输出操作的函数。以下是一些常见函数及其作用和示例：

### 1. `printf`函数
   - 作用：格式化输出到标准输出（通常是控制台）。
   - 示例：
      ```c
      #include <stdio.h>

      int main() {
         int num = 10;
         printf("数字是：%d\n", num);
         return 0;
      }
      ```

### 2. `scanf`函数
   - 作用：从标准输入（通常是键盘）读取格式化输入。
   - 示例：
      ```c
      #include <stdio.h>

      int main() {
         int num;
         printf("请输入一个数字：");
         scanf("%d", &num);
         printf("你输入的数字是：%d\n", num);
         return 0;
      }
      ```

### 3. `fprintf`函数
   - 作用：格式化输出到指定的文件流。
   - 示例：
      ```c
      #include <stdio.h>

      int main() {
         FILE *fp = fopen("output.txt", "w");
         if (fp!= NULL) {
            int num = 20;
            fprintf(fp, "数字是：%d\n", num);
            fclose(fp);
         }
         return 0;
      }
      ```

### 4. `fscanf`函数
   - 作用：从指定的文件流读取格式化输入。
   - 示例：
      ```c
      #include <stdio.h>

      int main() {
         FILE *fp = fopen("input.txt", "r");
         if (fp!= NULL) {
            int num;
            fscanf(fp, "%d", &num);
            printf("从文件中读取的数字是：%d\n", num);
            fclose(fp);
         }
         return 0;
      }
      ```

### 5. `putchar`函数
   - 作用：向标准输出输出一个字符。
   - 示例：
      ```c
      #include <stdio.h>

      int main() {
         char ch = 'A';
         putchar(ch);
         putchar('\n');
         return 0;
      }
      ```

### 6. `getchar`函数
   - 作用：从标准输入读取一个字符。
   - 示例：
      ```c
      #include <stdio.h>

      int main() {
         char ch = getchar();
         printf("你输入的字符是：%c\n", ch);
         return 0;
      }
      ```

### 7. `fputs`函数
   - 作用：将一个字符串写入指定的文件流，不自动添加换行符。
   - 示例：
      ```c
      #include <stdio.h>

      int main() {
         FILE *fp = fopen("output.txt", "w");
         if (fp!= NULL) {
            fputs("这是一行文本", fp);
            fclose(fp);
         }
         return 0;
      }
      ```

### 8. `fgets`函数
   - 作用：从指定的文件流读取一行文本，存储到指定的字符数组中。
   - 示例：
      ```c
      #include <stdio.h>

      int main() {
         FILE *fp = fopen("input.txt", "r");
         if (fp!= NULL) {
            char buffer[100];
            fgets(buffer, 100, fp);
            printf("从文件中读取的文本：%s", buffer);
            fclose(fp);
         }
         return 0;
      }
      ```