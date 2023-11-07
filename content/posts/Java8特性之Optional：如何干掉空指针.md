---
title: "Java8特性之Optional：如何干掉空指针"
date: 2023-06-30T11:12:42+08:00
draft: false
---
## 什么场景用Optional
#### 1、场景一
```
PatientInfo patientInfo = patientInfoDao.getPatientInfoById(consultOrder.getPatientId());
if (patientInfo != null) {
    consultInfoResp.setPatientHead(patientInfo.getHead());
}

// 使用Optional 和函数式编程，一行搞定，而且像说话一样
Optional.ofNullable(patientInfo).ifPresent(p -> consultInfoResp.setPatientHead(p.getHead()));
```
#### 2、场景二
```
public void test1() throws Exception {
    Student student = new Student(null, 3);
    if (student == null || isEmpty(student.getName())) {
        throw new Exception();
    }
    String name = student.getName();
    // 业务省略...

    // 使用Optional改造
    Optional.ofNullable(student).filter(s -> !isEmpty(s.getName())).orElseThrow(() -> new Exception());
}

public static boolean isEmpty(CharSequence str) {
    return str == null || str.length() == 0;
}
```
#### 3、场景三
```
public static String getChampionName(Competition comp) throws IllegalArgumentException {
    if (comp != null) {
        CompResult result = comp.getResult();
        if (result != null) {
            User champion = result.getChampion();
            if (champion != null) {
                return champion.getName();
            }
        }
    }
    throw new IllegalArgumentException("The value of param comp isn't available.");
}
这个在开发中是很常见的一种逻辑。去判读传进来的参数时候为空，或者是从数据库中获取的对象。由于某些原因，我们不能很流程的直接这样写。

comp.getResult().getChampion().getName()
上面的写法用Optional改写：

public static String getChampionName(Competition comp) throws IllegalArgumentException {
    return Optional.ofNullable(comp)
            .map(Competition::getResult)  // 相当于c -> c.getResult()，下同
            .map(CompResult::getChampion)
            .map(User::getName)
            .orElseThrow(()->new IllegalArgumentException("The value of param comp isn't available."));
}
```
#### 4、场景四
```
类型之间的转换，并且当没有值的时候返回一个默认值

int timeout = Optional.ofNullable(redisProperties.getTimeout())
       .map(x -> Long.valueOf(x.toMillis()).intValue())
       .orElse(10000);
```
