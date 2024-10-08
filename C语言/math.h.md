`<math.h>`头文件中包含了众多用于数学运算的函数，以下是一些常见的函数及其作用和示例：

### 1. 三角函数
   - `double sin(double x)`：计算弧度角`x`的正弦值。
      - 示例：
         ```c
         double radians = 0.5;
         double sineValue = sin(radians);
         printf("sin(%f) = %f\n", radians, sineValue);
         ```
   - `double cos(double x)`：计算弧度角`x`的余弦值。
      - 示例：
         ```c
         double radians = 0.5;
         double cosineValue = cos(radians);
         printf("cos(%f) = %f\n", radians, cosineValue);
         ```
   - `double tan(double x)`：计算弧度角`x`的正切值。
      - 示例：
         ```c
         double radians = 0.5;
         double tangentValue = tan(radians);
         printf("tan(%f) = %f\n", radians, tangentValue);
         ```

### 2. 反三角函数
   - `double asin(double x)`：计算`x`的反正弦值，结果介于$(-\pi/2, \pi/2)$。
      - 示例：
         ```c
         double value = 0.5;
         double arcsineValue = asin(value);
         printf("asin(%f) = %f\n", value, arcsineValue);
         ```
   - `double acos(double x)`：计算`x`的反余弦值，结果介于$(0, \pi)$。
      - 示例：
         ```c
         double value = 0.5;
         double arccosineValue = acos(value);
         printf("acos(%f) = %f\n", value, arccosineValue);
         ```
   - `double atan(double x)`：计算`x`的反正切值，结果介于$(-\pi/2, \pi/2)$。
      - 示例：
         ```c
         double value = 1.0;
         double arctangentValue = atan(value);
         printf("atan(%f) = %f\n", value, arctangentValue);
         ```
   - `double atan2(double y, double x)`：计算给定直角坐标系中点`(x, y)`的反正切函数值，结果介于$(-\pi, \pi)$，`y`和`x`的值的符号决定了正确的象限。
      - 示例：
         ```c
         double y = 1.0;
         double x = 1.0;
         double arctan2Value = atan2(y, x);
         printf("atan2(%f, %f) = %f\n", y, x, arctan2Value);
         ```

### 3. 双曲三角函数
   - `double sinh(double x)`：计算弧度角`x`的双曲正弦值。
      - 示例：
         ```c
         double radians = 0.5;
         double hyperbolicSineValue = sinh(radians);
         printf("sinh(%f) = %f\n", radians, hyperbolicSineValue);
         ```
   - `double cosh(double x)`：计算弧度角`x`的双曲余弦值。
      - 示例：
         ```c
         double radians = 0.5;
         double hyperbolicCosineValue = cosh(radians);
         printf("cosh(%f) = %f\n", radians, hyperbolicCosineValue);
         ```
   - `double tanh(double x)`：计算弧度角`x`的双曲正切值。
      - 示例：
         ```c
         double radians = 0.5;
         double hyperbolicTangentValue = tanh(radians);
         printf("tanh(%f) = %f\n", radians, hyperbolicTangentValue);
         ```

### 4. 指数与对数函数
   - `double exp(double x)`：计算自然数`e`的`x`次幂。
      - 示例：
         ```c
         double power = 2.0;
         double exponentialValue = exp(power);
         printf("exp(%f) = %f\n", power, exponentialValue);
         ```
   - `double log(double x)`：计算`x`的自然对数（以`e`为底的对数）。
      - 示例：
         ```c
         double value = 10.0;
         double naturalLogValue = log(value);
         printf("log(%f) = %f\n", value, naturalLogValue);
         ```
   - `double log10(double x)`：计算`x`的常用对数（以 10 为底的对数）。
      - 示例：
         ```c
         double value = 100.0;
         double commonLogValue = log10(value);
         printf("log10(%f) = %f\n", value, commonLogValue);
         ```

### 5. 幂函数
   - `double pow(double x, double y)`：计算`x`的`y`次幂。
      - 示例：
         ```c
         double base = 2.0;
         double exponent = 3.0;
         double powerValue = pow(base, exponent);
         printf("%f raised to the power of %f is %f\n", base, exponent, powerValue);
         ```

### 6. 取整函数
   - `double ceil(double x)`：向上取整，返回不小于`x`的最小整数。
      - 示例：
         ```c
         double value = 3.14;
         double ceilingValue = ceil(value);
         printf("ceil(%f) = %f\n", value, ceilingValue);
         ```
   - `double floor(double x)`：向下取整，返回不大于`x`的最大整数。
      - 示例：
         ```c
         double value = 3.14;
         double floorValue = floor(value);
         printf("floor(%f) = %f\n", value, floorValue);
         ```

### 7. 绝对值函数
   - `double fabs(double x)`：计算实数`x`的绝对值。
      - 示例：
         ```c
         double value = -5.0;
         double absoluteValue = fabs(value);
         printf("fabs(%f) = %f\n", value, absoluteValue);
         ```

### 8. 取余函数
   - `double fmod(double x, double y)`：计算`x`除以`y`的余数。
      - 示例：
         ```c
         double dividend = 10.0;
         double divisor = 3.0;
         double remainder = fmod(dividend, divisor);
         printf("%f mod %f = %f\n", dividend, divisor, remainder);
         ```

### 9. 其他函数
   - `double hypot(double x, double y)`：已知直角三角形两个直角边长度`x`和`y`，求斜边长度。
      - 示例：
         ```c
         double side1 = 3.0;
         double side2 = 4.0;
         double hypotenuse = hypot(side1, side2);
         printf("Hypotenuse of a right triangle with sides %f and %f is %f\n", side1, side2, hypotenuse);
         ```
   - `double frexp(double value, int *exp)`：将浮点数`value`分解为尾数和指数，并将指数存入`exp`中，即`value = mantissa * 2^exp`。
      - 示例：
         ```c
         double value = 10.0;
         int exponent;
         double mantissa = frexp(value, &exponent);
         printf("%f = %f * 2^%d\n", value, mantissa, exponent);
         ```
   - `double ldexp(double x, int exponent)`：计算`x`乘以 2 的`exponent`次幂。
      - 示例：
         ```c
         double value = 2.0;
         int exp = 3;
         double result = ldexp(value, exp);
         printf("%f * 2^%d = %f\n", value, exp, result);
         ```
   - `double modf(double x, double *intpart)`：将`x`拆分为整数部分和小数部分，并将整数部分存储在`intpart`中，返回值为小数部分。
      - 示例：
         ```c
         double value = 3.14;
         double integerPart;
         double fractionalPart = modf(value, &integerPart);
         printf("%f = %f + %f\n", value, integerPart, fractionalPart);
         ```