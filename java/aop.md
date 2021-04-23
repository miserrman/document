# aop记录

### 2021年4月24日

今天使用aop,希望获取到函数返回后的值

首先声明切点
```java

@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface Audit {

}
```

正确的代码示例
```java
@Component
@Aspect
public class AuditAop {

    @Pointcut("@annotation(com.longyan.policy.annotation.Audit)")
    private void cutPoint() {

    }
    //原先使用pointcut="@within(...)和@annotation都失败了，可以使用这个切点"
    @AfterReturning(pointcut = "cutPoint()", returning = "val")
    public void after(JoinPoint joinPoint, Object val) {
        return;
    }
}
```