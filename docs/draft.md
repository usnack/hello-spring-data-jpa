# Core Concepts

4단계 프로세스로 쿼리를 정의한다.
1. Repository 구현 인터페이스 선언
2. query method 선언
3. proxy instance를 만들 수 있도록 설정 (```@EnableJpaRepositories``)
4. 해당 인터페이스를 DI하여 사용




## Repository 구현 인터페이스 선언

- ```CrudRepository``` 인터페이스를 구현하는 것이 전형적
- version 3.0 부터 ListCrudRepository 도 제공
- reactive store
    - ```ReactiveCrudRepository```
    - ```RxJava3CrudRepository```
- kotlin's coroutines
    - ```CoroutineCrudRepository```

Spring Data에서 제공하는 인터페이스를 사용하지 않는 경우 ```@RepositoryDefinition```로 어노테이션을 추가할 수 있다.
> CRUD 중 일부 만 제공하고 싶은 경우


proxy 객체를 만들지 않도록 하고자 하는 경우 ```@NoRepositoryBean``` 을 사용할 수 있다.
> 공통 인터페이스를 선언하여 사용하는 경우    


한 프로젝트에서 여러개의 데이터 모듈(jpa, mongodb, elastic search...)를 가져야하는 경우 
interface, 또는 도메인 클래스의 정의에 따른 엄격한 설정 모드로 진입한다. (strict repository configration mode)
- interface : ```extends JpaRepository```   
- domain class : ```@Entity```, ```@Document```    
💡 두가지 모듈을 같이 사용할 수는 있다 (테스트 필요)


## Query Method 선언    







