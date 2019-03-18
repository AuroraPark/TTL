# 선택정렬



## java
```
import java.util.Arrays;

public class SelectionSortEx {
	public static void main(String[] args) {
		int[] list = { 1, 3, 4, 9, 7, 6 };
		int least = 0;
		int temp = 0;
		
		System.out.println("정렬할 배열 : " + Arrays.toString(list));
		for (int i = 0; i < list.length - 1; i++) {
			least = i;
			for (int j = i + 1; j < list.length; j++) {
				if (list[j] < list[least]) {
					least = j;

					temp = list[i];
					list[i] = list[least];
					list[least] = temp;

				} // if
			} // 내부 for문
			System.out.println("[" + i + "] 번째 선택정렬 중 :" + Arrays.toString(list));
		} // 외부 for문
			// 결과
		System.out.println("선택정렬 결과 : " + Arrays.toString(list));
	}
}
```


## C

```
#define  SWAP(x, y, t) ( (t) = (x), (x) = (y), (y) = (t) )
  
void  selection_sort(int list[], int n)
{
	int i, j, least, temp;
	for ( i =  0; i < n -  1; i++ ) {
	least = i;
		for ( j = i +  1; j < n; j++) {
				if (list[j] < list[least]) least = j;
		SWAP(list[i], list[least], temp);
		}
	}
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcyOTE2MzA0M119
-->