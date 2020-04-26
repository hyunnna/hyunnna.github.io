---
layout: post
title:  "Difference-Of-Java-Version"
date:   2020-04-18T14:25:52-05:00
author: hyunnna
categories: learning
---

**Java version 에 따른 차이점**
============

>**Java 7**
--------

>1. 타입추론 (Type Inference)
>
>2. Switch 문 문자열 case
  switch ~ case 문에 문자열이 가능해짐
>
>3.Catching Multiple Exception Type in Single Catch Block
  멀티 catch 가능
>
>4.이진수 표현


***

>**Java 8**
--------
>1.Lambda
>  컴파일러에게 실질적 구현을 시키는 방식
>
>2.interface 클래스에 구현체 작성가능
>  dafalut와 static 키워드를 사용해서 구현 메소드를 interface에 작성할 수 있게 됨
>
>3.다양한 DateTime 추가
>
>4.Optional
> optional은 null이 될 수도 있는 객체를 감싸는 일종의 래퍼 클래스이다.
>   null 체크를 최대한 하지 않고도 코딩할 수 있게 됨

***

>**Java 9**
--------
>1.인터페이스 내에 private 구현체 가능
>2.모듈시스템 등장
>  기존 jar 방식을 개선하기 위해 등장

***

>**Java 10**
---------
>1.Local Vaiable Type Inference 에서 var 사용
>2.JVM heap 영역을 NVDIMM (비휘발성 NAND 플래시 메모리) 혹은 사용자 지정과 같은 대체 메모리 장치에 할당 가능
---------