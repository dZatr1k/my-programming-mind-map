Mathf - это статический класс в пространстве имён UnityEngine, позволяющий работать с векторами и числами.

Статические свойства:
1. Deg2Rad - число, переводящее из градусов в радианы (Read Only).
2. Rad2Deg - число, переводящее из радианы в градусы (Read Only).
3. Epsilon - число, необходимое для сравнения чисел с плавающей точкой (Read Only).
4. Infinity - число, представляющее положительную бесконечность (Read Only).
5. NegativeInfinity - число, представляющее отрицательную бесконечность (Read Only).
6. PI - число пи (Read Only).

Статические методы:
1. float Abs(f) - возвращает абсолютное число f.
2. float Acos(f) - возвращает арккосинус числа f.
3. float Asin(f) - возвращает арксинус числа f.
4. float Atan(f) - возвращает арктангенс числа f.
5. float Atan2(f, g) - возвращает арктангенс f/g.
6. bool Approximately(f, g) - возвращает true, если f == g, причём всегда, независимо от погрешности, возникающей в числах с плавающей точкой.
7. float Ceil(f) - возвращает самое маленькое целое число, близкое f.
8. int CeilToInt(f) - то же самое, что Ceil.
9. Floor -
10. FloorToInt - 
11. float Clamp(f, min, max) - возвращает число f, если оно в переделах [min, max], иначе либо min, либо max
12. float Clamp01(f) - то же самое, что Clamp, но min=0, а max=1
13. int ClosestPowerOfTwo(f) - возвращают самую близкую степень двойки к числу f.
14. CorrelatedColorTemperatureToRGB - 
15. Cos -
16. Sin -
17. Tan - 
18. DeltaAngle - 
19. Exp - 
20. FloatToHalf -
21.  GammaToLinearSpace -
22. LinearToGammaSpace
23. HalfToFloat -
24. Lerp -
25. InverseLerp -
26. LerpAngle -
27. LerpUnclumped - 
28. IsPowerOfTwo - 
29. Log -
30. Log10 -
31. Max -
32. Min -
33. MoveTowerds -
34. MoveTowerdsAngle - 
35. NextPowerOfTwo -
36. PerlinNoise -
37. PerlinNoise1D -
38. PingPong - 
39. Pow -
40. Repeat - 
41. float Round(f) - возвращает округлённое число f.
42. int RoundToInt(f) - то же самое, что и Round.
43. float Sign(f) - возвращает -1, если f < 0, иначе 1.
44. SmoothDamp -
45. SmoothDampAngle -
46. SmoothStep - 
47. Sqrt - 
#CSharp 