---
layout: post
title: "java stream api 예제"
categories: [Java]
description: "java stream api 예제"
keywords: Java, Stream api
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---


```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

public class StreamExample {
    public static void main(String[] args) {
        // Person 객체 생성
        List<Person> personList = new ArrayList<>();
        personList.add(new Person("Alice", 25, "Seoul", 3000));
        personList.add(new Person("Bob", 30, "New York", 4000));
        personList.add(new Person("Charlie", 35, "London", 5000));
        personList.add(new Person("David", 40, "Tokyo", 6000));
        personList.add(new Person("Emma", 45, "Sydney", 7000));
        personList.add(new Person("Frank", 50, "Paris", 8000));
        personList.add(new Person("Grace", 55, "Berlin", 9000));
        personList.add(new Person("Henry", 60, "Moscow", 10000));
        personList.add(new Person("Ivy", 25, "Seoul", 3000));
        personList.add(new Person("Jack", 30, "New York", 4000));
        personList.add(new Person("Kate", 35, "London", 5000));
        personList.add(new Person("Leo", 40, "Tokyo", 6000));
        personList.add(new Person("Mia", 45, "Sydney", 7000));
        personList.add(new Person("Nick", 50, "Paris", 8000));
        personList.add(new Person("Olivia", 55, "Berlin", 9000));
        personList.add(new Person("Peter", 60, "Moscow", 10000));
        personList.add(new Person("Queen", 25, "Seoul", 3000));
        personList.add(new Person("Ryan", 30, "New York", 4000));
        personList.add(new Person("Sarah", 35, "London", 5000));
        personList.add(new Person("Tom", 40, "Tokyo", 6000));
        
        // Stream API 사용 예시
        // 1. filter를 사용하여 거주지가 "Seoul"인 사람들을 필터링
        List<Person> seoulPeople = personList.stream()
                .filter(person -> person.getResidence().equals("Seoul"))
                .collect(Collectors.toList());

        // 2. map을 사용하여 각 사람의 월급을 10% 증가시키기
        List<Integer> increasedSalary = personList.stream()
                .map(person -> person.getSalary() * 1.1)
                .map(Double::intValue)
                .collect(Collectors.toList());

        // 3. sorted를 사용하여 나이가 많은 순서로 정렬하기
        List<Person> sortedByAge = personList.stream()
                .sorted((p1, p2) -> Integer.compare(p2.getAge(), p1.getAge()))
                .collect(Collectors.toList());

        // 4. distinct를 사용하여 거주지가 중복되지 않도록 필터링
        List<String> distinctResidences = personList.stream()
                .map(Person::getResidence)
                .distinct()
                .collect(Collectors.toList));
       // 5. reduce를 사용하여 월급이 가장 높은 사람 구하기
      Person highestSalaryPerson = personList.stream()
                .reduce((p1, p2) -> p1.getSalary() > p2.getSalary() ? p1 : p2)
                .orElse(null);
      System.out.println("Highest salary person: " + highestSalaryPerson.getName());
```
