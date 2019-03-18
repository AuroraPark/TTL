# 버블정렬

서로 인접한 두 원소를 검사하여 정렬하는 알고리즘
인접한 2개의 레코드를 비교하여 크기가 순서대로 되어 있지 않으면 서로 교환한다.

> T(n) = O(n^2)

## java

```
import java.util.Arrays;

public class bubble_sort {
	public static void main(String[] args) {
		int[] list = { 1, 3, 4, 9, 7, 6 };

		// 버블정렬
		System.out.println("정렬할 배열 : " + Arrays.toString(list));

		for (int i = 0; i < list.length; i++) {
			boolean changed = false; // 자리바꿈이 발생 하는 지를 체크한다.

			for (int j = 0; j < list.length - i - 1; j++) {
				if (list[j] > list[j + 1]) { // 옆의 값이 작으면 바꾼다.
					int temp = list[j];
					list[j] = list[j + 1];
					list[j + 1] = temp;
					changed = true; // 자리바꿈이 발생하였으니 true로
				}
			} // end for j

			if (!changed)
				break; // 자리바꿈이 없으면 반복문을 끝낸다.

			
				System.out.println("[" + i+ "] 번째 정렬 : " + Arrays.toString(list));
			
		} // end for i
		System.out.println("정렬된 배열 : " + Arrays.toString(list));
	}// end main
}

```

```
버블정렬
 * 정렬할 배열 : [1, 3, 4, 9, 7, 6]
[0] 번째 정렬 : [1, 3, 4, 7, 6, 9]
[1] 번째 정렬 : [1, 3, 4, 7, 6, 9]
[2] 번째 정렬 : [1, 3, 4, 7, 6, 9]
[3] 번째 정렬 : [1, 3, 4, 7, 6, 9]
[4] 번째 정렬 : [1, 3, 4, 7, 6, 9]
[5] 번째 정렬 : [1, 3, 4, 7, 6, 9]
[0] 번째 정렬 : [1, 3, 4, 6, 7, 9]
[1] 번째 정렬 : [1, 3, 4, 6, 7, 9]
[2] 번째 정렬 : [1, 3, 4, 6, 7, 9]
[3] 번째 정렬 : [1, 3, 4, 6, 7, 9]
[4] 번째 정렬 : [1, 3, 4, 6, 7, 9]
[5] 번째 정렬 : [1, 3, 4, 6, 7, 9]
정렬된 배열 : [1, 3, 4, 6, 7, 9]

```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAxODM1OTAwMSwxNjI1MzA3NzI1LDczMD
k5ODExNl19
-->