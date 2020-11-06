# 문제풀이

###Insertion Sort List
<p>
  구현 : 반복문(while)
  n개의 노드가 들어있는 list * n개의 노드가 들어있는 result list
  시간복잡도 : O(n²)
</p>

결과값을 저장할 result변수를 노드와 노드 사이에 값을 넣을수있도록 생성
```
  let result = new ListNode(null,new ListNode(head.val,null));
  //result -> null -> 3
```

새로운 노드(tmp)를 생성해주고 result_point라는 result 리스트의 헤더를 초기화함
```
  let tmp = new ListNode(head.val,null);
  let result_point = result; 
```

반복문을 통해서 값을 비교하고 result_point로 위치를 이동하면서 정렬시킴
```
  while(result_point !== null){
    if(result_point.next === null){
        result_point.next = tmp;
        break;
    }
    if(result_point.next.val > tmp.val){
        tmp.next = result_point.next;
        result_point.next = tmp;
        break;
    }
    result_point = result_point.next;
  }
```

```
  예시(4->2->1->3)
  (1)
   tmp -> 2
   result -> null -> 4
   
```

