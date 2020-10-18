---
title:  "[java] equals"
excerpt: "프로젝트"
toc: true
author_profile: false
toc_sticky: true
categories:
- project
tags:
- java
- equals
- hashCode
---
## [Java] equals()와 hashcode() 재정의
- equals() - 두 객체를 비교하여 서로 같은 객체인지 판단하는 함수

- hashcode() - 객체의 주소값을 변환하여 생성한 객체의 고유한 정수값을 만들어주는 함수


## equals()
- 재정의(override) 하는 이유
	- equals는 기본적으로 주소 값을 이용해서 같은지 판단

	- 논리적으로 같은 객체라고 판단하기 위해서는 재정의가 필요

		- ex) Car car1 = new Car(“소나타”), car2 = new Car(“소나타”)의 경우 같은 “소나타”이지만 재정의를 하지 않으면 다른다고 판단


- equals 메서드 규약
	- 반사성(reflexivity) - x.equals(x)는 true

	- 대칭성(symmetry) - x.equals(y)가 true이면 y.equals(x)도 true

	- 추이성(transitivity) - x.equals(y)가 true이고 y.equals(z)도 true이면 x.equals(z)도 true

	- 일관성(consistency) - x.equals(y)를 몇번해도 항상 true 또는 false를 반환

	- x.equals(null)는 false 


## hashCode()
- 재정의(override)가 필요한 이유
	- 같은 값을 가진 객체가 서로 다른 해시 값을 갖게 되기 때문에

	- HashSet or HashMap에 객체를 넣을 때 필요
		- 재정의를 안할 경우 NullPointerException 발생


## equals()와 hashCode() 둘 다 재정의를 해야 하는 이유
- equals()만 하면 논리적으로 같은 객체도 해시 값이 다르기 때문에 다르다고 판단

- hashCode()만 하면 해시 값은 같아도 논리적으로 같은 객체인지 알 수가 없다고 판단(null 리턴)

## 예제 코드 
```java
class Point{
	int y;
	int x;
	Point(int y, int x){
		this.y=y;
		this.x=x;
	}
	@Override
	public boolean equals(Object o){
		//자신과 같은 객체
		if(this == o){
			return true;
		}
		// 같은 타입의 객체인지 판단
		if(!(o instanceof Point)){
			return false;
		}
		Point point =(Point) o;
		// 논리적으로 같은 값인지 판단
		if(this.y==point.y && this.x==point.x){
			return true;
		}else{
			return false;
		}
	}
	@Override
	public int hashCode(){
		return Objects.hash(this.y, this.x);
	}
}
```