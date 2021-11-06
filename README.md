# В pom.xml добавлена поддержка spotbugs-maven-plugin

```xml
    <build>
        <plugins>
            <plugin>
                <groupId>com.github.spotbugs</groupId>
                <artifactId>spotbugs-maven-plugin</artifactId>
                <version>3.1.12.2</version>
            </plugin>
        </plugins>
    </build>
```

# Код Java находящийся в этом репозитории

```Java
public class Main {
  public static void main(String[] args) {
    BonusService service = new BonusService();

    long amount = 1000_60;
    boolean registered = true;

    long calculate = service.calculate(amount, registered);
    System.out.println(calculate);
  }
}
```
```Java
public class BonusService {
  public long calculate(long amount, boolean registered) {
    int percent = registered ? 3 : 1;
    long bonus = amount * percent / 100 / 100;
    long limit = 500;
    if (bonus > limit) {
      bonus = limit;
    }
    return bonus;
  }
}
```