`<stdlib.h>`头文件中包含了很多实用的函数，以下是一些常见函数及其作用，并附上示例：

### 1. 内存管理函数
   - `void *malloc(size_t size)`：从堆上分配指定大小的内存块，返回指向分配内存的指针。如果分配失败，返回 `NULL`。
      - 示例：
         ```c
         int *arr = (int *)malloc(5 * sizeof(int));
         if (arr!= NULL) {
            for (int i = 0; i < 5; i++) {
               arr[i] = i;
            }
            // 使用分配的内存
            free(arr);
         }
         ```
   - `void *calloc(size_t num, size_t size)`：分配 `num` 个大小为 `size` 的内存块，并将其初始化为零。返回指向分配内存的指针，失败则返回 `NULL`。
      - 示例：
         ```c
         int *arr = (int *)calloc(3, sizeof(int));
         if (arr!= NULL) {
            // 分配的内存初始化为零
            for (int i = 0; i < 3; i++) {
               printf("%d ", arr[i]);
            }
            free(arr);
         }
         ```
   - `void *realloc(void *ptr, size_t size)`：调整先前由 `malloc`、`calloc` 或 `realloc` 分配的 `ptr` 所指向的内存块的大小为 `size`。返回指向调整后内存块的指针，失败则返回 `NULL`。
      - 示例：
         ```c
         int *arr = (int *)malloc(2 * sizeof(int));
         arr[0] = 1;
         arr[1] = 2;
         arr = (int *)realloc(arr, 4 * sizeof(int));
         if (arr!= NULL) {
            arr[2] = 3;
            arr[3] = 4;
            // 使用调整后的内存
            free(arr);
         }
         ```
   - `void free(void *ptr)`：释放由 `malloc`、`calloc` 或 `realloc` 分配的内存块。

### 2. 数值转换函数
   - `int atoi(const char *str)`：将字符串 `str` 转换为整数。如果 `str` 不能转换为整数，返回 0。
      - 示例：
         ```c
         char str[] = "123";
         int num = atoi(str);
         printf("%d\n", num); // 输出 123
         ```
   - `long atol(const char *str)`：将字符串 `str` 转换为长整数。
      - 示例：
         ```c
         char str[] = "456";
         long num = atol(str);
         printf("%ld\n", num); // 输出 456
         ```
   - `double atof(const char *str)`：将字符串 `str` 转换为浮点数。
      - 示例：
         ```c
         char str[] = "3.14";
         double num = atof(str);
         printf("%f\n", num); // 输出 3.14
         ```

### 3. 随机数生成函数
   - `void srand(unsigned int seed)`：设置随机数生成器的种子。
      - 示例：
         ```c
         srand(time(NULL)); // 使用当前时间作为种子
         ```
   - `int rand(void)`：生成随机整数。每次调用 `rand` 函数都会根据当前种子生成一个新的随机数。
      - 示例：
         ```c
         int random_num = rand();
         printf("%d\n", random_num);
         ```

### 4. 其他函数
   - `void abort(void)`：使程序异常终止。
      - 示例：
         ```c
         // 在某些特定条件下终止程序
         if (some_condition) {
            abort();
         }
         ```
   - `int abs(int j)`：返回整数 `j` 的绝对值。
      - 示例：
         ```c
         int num = -5;
         int abs_num = abs(num);
         printf("%d\n", abs_num); // 输出 5
         ```
   - `div_t div(int numer, int denom)`：将两个整数相除，返回一个包含商和余数的结构体。
      - 示例：
         ```c
         div_t result = div(10, 3);
         printf("商：%d，余数：%d\n", result.quot, result.rem); // 输出商：3，余数：1
         ```
   - `void qsort(void *base, size_t nmemb, size_t size, int (*compar)(const void *, const void *))`：对一个数组进行快速排序。用户需要提供一个比较函数 `compar`，用于确定两个元素的顺序。
      - 示例：
         ```c
         int arr[] = {5, 2, 8, 1, 7};
         int n = sizeof(arr) / sizeof(arr[0]);
         qsort(arr, n, sizeof(int), [](const void *a, const void *b) {
            int arg1 = *(int *)a;
            int arg2 = *(int *)b;
            if (arg1 < arg2) return -1;
            if (arg1 > arg2) return 1;
            return 0;
         });
         for (int i = 0; i < n; i++) {
            printf("%d ", arr[i]);
         }
         // 输出 1 2 5 7 8
         ```