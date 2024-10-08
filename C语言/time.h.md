`<time.h>`头文件中包含了用于处理时间和日期的函数，以下是一些常见的函数及其作用和示例：

### 1. `time_t time(time_t *tloc)`
   - 作用：返回自纪元（通常是 1970 年 1 月 1 日 00:00:00 UTC）以来经过的秒数。如果`tloc`不为`NULL`，则同时将返回值存储在`tloc`所指向的位置。
   - 示例：
      ```c
      #include <stdio.h>
      #include <time.h>

      int main() {
         time_t currentTime;
         time(&currentTime);
         printf("当前时间的秒数：%ld\n", currentTime);
         return 0;
      }
      ```

### 2. `struct tm *gmtime(const time_t *timer)`
   - 作用：将`time_t`类型的时间（自纪元以来的秒数）转换为协调世界时（UTC）的分解时间形式，以`struct tm`结构体表示。
   - 示例：
      ```c
      #include <stdio.h>
      #include <time.h>

      int main() {
         time_t currentTime;
         time(&currentTime);
         struct tm *utcTime = gmtime(&currentTime);
         printf("UTC 时间：%d-%d-%d %d:%d:%d\n", utcTime->tm_year + 1900, utcTime->tm_mon + 1, utcTime->tm_mday, utcTime->tm_hour, utcTime->tm_min, utcTime->tm_sec);
         return 0;
      }
      ```

### 3. `struct tm *localtime(const time_t *timer)`
   - 作用：与`gmtime`类似，但返回本地时间的分解形式。
   - 示例：
      ```c
      #include <stdio.h>
      #include <time.h>

      int main() {
         time_t currentTime;
         time(&currentTime);
         struct tm *localTime = localtime(&currentTime);
         printf("本地时间：%d-%d-%d %d:%d:%d\n", localTime->tm_year + 1900, localTime->tm_mon + 1, localTime->tm_mday, localTime->tm_hour, localTime->tm_min, localTime->tm_sec);
         return 0;
      }
      ```

### 4. `char *ctime(const time_t *timep)`
   - 作用：将`time_t`类型的时间转换为字符串形式，格式为“星期 月 日 时:分:秒 年”。
   - 示例：
      ```c
      #include <stdio.h>
      #include <time.h>

      int main() {
         time_t currentTime;
         time(&currentTime);
         char *timeString = ctime(&currentTime);
         printf("时间字符串：%s", timeString);
         return 0;
      }
      ```

### 5. `size_t strftime(char *s, size_t maxsize, const char *format, const struct tm *timeptr)`
   - 作用：根据指定的格式字符串`format`，将`struct tm`结构体表示的时间格式化为字符串，并存储在`s`中。`maxsize`指定了`s`的最大长度。
   - 示例：
      ```c
      #include <stdio.h>
      #include <time.h>

      int main() {
         time_t currentTime;
         time(&currentTime);
         struct tm *localTime = localtime(&currentTime);
         char buffer[80];
         strftime(buffer, 80, "%Y-%m-%d %H:%M:%S", localTime);
         printf("格式化后的时间：%s\n", buffer);
         return 0;
      }
      ```