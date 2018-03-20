---
layout: post
title:  "Structural Patterns"
date:   2018-03-20 16:03:33
permalink: /first-post.html
---

# Ch4 - Structural Patterns

## Proxy Pattern
- 실제 객체를 대신하는 프록시 객체를 사용해서 실제 객체의 생성이나 접근 등을 제어할수 있도록 해주는 패턴.
 - remote proxy, virtual proxy, protection proxy
- Objectives
 - Hide an object behind the proxy
 - Provide a new abstraction layer
- The [proxy pattern](https://en.wikipedia.org/wiki/Proxy_pattern) provides an object that controls access to another object, intercepting all calls.

### implementation:
```go
    // To use proxy and to object they must implement same methods
    type IObject interface {
        ObjDo(action string)
    }

    // Object represents real objects which proxy will delegate data
    type Object struct {
        action string
    }

    // ObjDo implements IObject interface and handel's all logic
    func (obj *Object) ObjDo(action string) {
        // Action behavior
        fmt.Printf("I can, %s", action)
    }

    // ProxyObject represents proxy object with intercepts actions
    type ProxyObject struct {
        object *Object
    }

    // ObjDo are implemented IObject and intercept action before send in real Object
    func (p *ProxyObject) ObjDo(action string) {
        if p.object == nil {
            p.object = new(Object)
        }
        if action == "Run" {
            p.object.ObjDo(action) // Prints: I can, Run
        }
    }
```
