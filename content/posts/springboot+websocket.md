---
title: "Springboot+websocket"
date: 2024-04-29T17:35:17+08:00
draft: true
---

1. pom.xml引入spring-boot-starter-websocket依赖
```
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-websocket</artifactId>
</dependency>
```
2. WebSocketConfig配置
```
@Configuration
@EnableWebSocket
public class WebSocketConfig implements WebSocketConfigurer {

    @Override
    public void registerWebSocketHandlers(WebSocketHandlerRegistry registry) {
        registry.addHandler(webSocketHandler(), "/webSocketHandler").setAllowedOrigins("*");;
    }

    @Bean
    public WebSocketHandler webSocketHandler() {
        return new WebSocketHandler();
    }
}
```
3. TextWebSocketHandler处理，建立连接、断开连接

```
public class WebSocketHandler extends TextWebSocketHandler  {



    @Override
    public void afterConnectionEstablished(WebSocketSession session) throws Exception {
        String query = session.getUri().getQuery();
        System.err.println("建立websocket连接");
        String[] queryArr = query.split("\\=");
        String token = queryArr[1];
        System.err.println("token:"+token);
        String userId = Jwts.parser()
                .setSigningKey("")
                .parseClaimsJws(token)
                .getBody()
                .getSubject();
        System.err.println("userid:"+userId);
        if(userId!=null && !UserCache.userMap.containsKey(userId)){
            UserCache.userMap.put(userId,session);
        }

    }


    @Override
    public void afterConnectionClosed(WebSocketSession session, CloseStatus status) throws Exception {
        System.err.println("断开websocket连接");
        String query = session.getUri().getQuery();
        String[] queryArr = query.split("\\=");
        String token = queryArr[1];
        System.err.println("token:"+token);
        String userId = Jwts.parser()
                .setSigningKey("")
                .parseClaimsJws(token)
                .getBody()
                .getSubject();
        System.err.println("userid:"+userId);
        if(userId!=null && UserCache.userMap.containsKey(userId)){
            UserCache.userMap.remove(userId);
        }


    }
}
```
