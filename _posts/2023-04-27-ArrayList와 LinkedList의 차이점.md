---
layout: post
title: ArrayList와 LinkedList의 차이점
categories: [Java]
description: ArrayList와 LinkedList의 차이점
keywords: Java, ArrayList와 LinkedList의 차이점
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---


ArrayList와 LinkedList는 둘 다 자바에서 제공하는 리스트 구현체입니다. 하지만 내부적으로 구현되는 방식이 다르기 때문에 각각의 특징이 있습니다.

ArrayList는 내부적으로 배열을 사용하여 요소를 저장하고, 요소의 추가나 삭제가 일어날 때 배열의 크기를 동적으로 변경합니다. 이러한 구현 방식 때문에 배열의 인덱스를 사용하여 요소를 빠르게 접근할 수 있습니다. 따라서 ArrayList는 요소의 검색과 수정이 빠르고, 순차적인 요소 추가 및 삭제에 비교적 느립니다.

LinkedList는 요소를 노드라는 객체로 구성된 연결리스트로 저장합니다. 각 노드는 자신의 데이터와 다음 노드를 가리키는 포인터를 가지고 있습니다. 따라서 LinkedList는 순차적인 요소 추가 및 삭제가 빠르고, 임의의 위치에서 요소를 추가하거나 삭제하는 것도 빠릅니다. 하지만 요소의 검색이나 수정은 연결리스트를 처음부터 끝까지 순회해야 하기 때문에 ArrayList보다는 느리다는 특징이 있습니다.


```java
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        // ArrayList vs LinkedList: 순차적인 요소 추가
        List<Integer> arrayList = new ArrayList<>();
        List<Integer> linkedList = new LinkedList<>();

        long startTime = System.nanoTime();

        for (int i = 0; i < 100000; i++) {
            arrayList.add(i);
        }

        long endTime = System.nanoTime();
        long duration = endTime - startTime;
        System.out.println("ArrayList 순차적인 요소 추가: " + duration + " ns");
        // ArrayList 순차적인 요소 추가: 25913 ns

        startTime = System.nanoTime();

        for (int i = 0; i < 100000; i++) {
            linkedList.add(i);
        }

        endTime = System.nanoTime();
        duration = endTime - startTime;
        System.out.println("LinkedList 순차적인 요소 추가: " + duration + " ns");
        // LinkedList 순차적인 요소 추가: 195087 ns

        // ArrayList vs LinkedList: 임의의 위치에서 요소 추가
        startTime = System.nanoTime();

        for (int i = 0; i < 10000; i++) {
            arrayList.add(0, i);
        }

        endTime = System.nanoTime();
        duration = endTime - startTime;
        System.out.println("ArrayList 임의의 위치에서 요소 추가: " + duration + " ns");
        // ArrayList 임의의 위치에서 요소 추가: 11515585 ns

        startTime = System.nanoTime();

        for (int i = 0; i < 10000; i++) {
            linkedList.add(0, i);
        }

        endTime = System.nanoTime();
        duration = endTime - startTime;
        System.out.println("LinkedList 임의의 위치에서 요소 추가: " + duration + " ns");
        // LinkedList 임의의 위치에서 요소 추가: 15893 ns
    }
}
``` 

위 결과를 보면, 순차적인 요소 추가에서는 `ArrayList`가 `LinkedList`보다 빠르고, 임의의 위치에서 요소 추가에서는 `LinkedList`가 `ArrayList`보다 빠른 것을 확인할 수 있습니다.