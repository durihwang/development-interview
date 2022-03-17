## 자주 사용하는 코드
```java
// array 중복 제거
Arrays.stream(report).distinct().toArray(String[]::new)

// Hashmap to int[]
result.values().stream().mapToInt(Integer::intValue).toArray();

// 순서를 보장해주는 map
new LinkedHashMap<>();

// 절대값 구하기
// 거리를 계산할 때 사용한다.
Math.abs();

// 이진수로 변환하고 앞에 0으로 자릿수 채우기
arr1_s[i] = String.format("%05d", Integer.parseInt(Integer.toBinaryString(arr1[i])));
```