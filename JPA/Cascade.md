# 영속성 전이(Cascade)
## 1.영속성 전이란
JPA에서 엔티티간의 관계를 관리할 때, 특정 엔티티의 상태 변경이 다른 엔티티에도 영향을 미치도록 설정하는 매커니즘을 의미한다.

## 2.Cascade타입
### JPA에서는 6가지의 Cascade 옵션을 제공하며, 엔티티 간 관계를 어떻게 설정하느냐에 따라 다음과 같이 사용할 수 있다.

#### - ALL : 모든 상태 변경에 대해 Cascade를 수행 (INSERT, UPDATE, DELETE)<br> 
#### - PERSIST : 부모 엔티티가 영속 상태로 전이될 때 자식 엔티티도 함께 영속 상태로 전이<br>
#### - MERGE : 부모 엔티티가 병합(merge)될 때 자식 엔티티도 함께 병합<br>
#### - REMOVE : 부모 엔티티가 삭제될 때 자식 엔티티도 함께 삭제<br>
#### - REFRESH : 부모 엔티티가 리프레시될 때 자식 엔티티도 함께 리프레시<br>
#### - DETACH : 부모 엔티티가 분리(detach)될 때 자식 엔티티도 함께 분리<br>

## 3.설정 예시
```
@Entity
public class Team{
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;

    @OneToMany(mappedBy = "team", cascade = CascadeType.ALL)
    private List<Player> player;
}
```

```
@Entity
public class Player {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    private String name;
    
    @OneToOne
    @JoinColumn(name = "team_id")
    private Team team;
}
```
 위의 Team Entity에서 `@OneToMany(mappedBy = "team", cascade = CascadeType.ALL)`처럼  CascadeType을 설정 해 줄 수 있다.