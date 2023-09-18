1. Java와 객체 지향 프로그래밍에 대해 정리하기
-Java는 C++와 같은 객체지향언어

-객체지향 프로그래밍 장단점: 코드 재사용성 높음, 유지보수 쉬움, 대형 프로젝트에 적합/ 처리 속도 상대적으로 느림, 객체 많으면 용량 커질 수 있음, 설계 시 많은 노력과 시간 필요

-객체지향 프로그래밍 특징: 추상화, 캡슐화, 상속, 다형성

-객체지향 설계 원칙
    1. 단일 책임 원칙: 하나의 클래스는 단 하나의 책임만 가져야 함
    2. 개방-폐쇠 원칙: 기능을 변경하거나 확장할 수 있으면서 기능을 사용하는 코드는 수정하지 않아야 함
    3. 리스코프 치환 원칙: 상위 타입의 객체를 하위 타입의 객체로 치환해도, 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 함
    4. 인터페이스 분리 원칙: 클라이언트가 필요로 하는 인터페이스로 분리함으로써 각 클라이언트가 사용하지 않는 인터페이스에 변경이 있어도 영향을 받지 않도록 해야 함
    5. 의존관계 역전 원칙: 고수준 모듈은 저수준 모듈의 구현에 의존해서는 안되고 저수는 모듈은 고수준 모듈에서 정의한 추상 타입에 의존해야 함

2. 프로그램 구현하기

package org.example;

public interface Calculator {
    int plus(int a, int b); // a + b 값 반환
    int minus(int a, int b); // a - b 값 반환
    int mul(int a, int b); // a * b 값 반환
    int div(int a, int b); // a / b 값 반환
}

class Cal implements Calculator{
    public int plus(int a, int b){
        return a+b;
    }
    public int minus(int a, int b){
        return a-b;
    }
    public int mul(int a, int b){
        return a*b;
    }
    public int div(int a, int b){
        return a/b;
    }
}

package org.example;

abstract class Animal {
    public abstract void speak();
}

class Cat extends Animal{
    private String name;
    public Cat(String name){
        this.name=name;
    }
    public void speak(){
        System.out.println(name+" says Meow!");
    }
}

class Dog extends Animal{
    private String name;
    public Dog(String name){
        this.name=name;
    }
    public void speak(){
        System.out.println(name+" says Woof!");
    }
}


package org.example;

public class Main {
    public static void main(String[] args) {
        Calculator calculator = new Cal();

        System.out.println("1234 + 4321 = " + calculator.plus(1234, 4321));
        System.out.println("911 - 170 = " + calculator.minus(911, 170));
        System.out.println("2 * 3 = " + calculator.mul(2, 3));
        System.out.println("33 / 11 = " + calculator.div(33, 11));

        System.out.println("\n");

        Cat cat = new Cat("cat"); // 다른 동물 하셔도 상관 없습니다!
        Dog dog = new Dog("dog");
        Animal[] animals = {cat, dog};
        for (Animal animal : animals) {
            animal.speak();
        }
    }
}

