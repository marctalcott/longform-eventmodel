---
agg:
  - - user
us: 123345
pt: 5
longform:
---

## meta:
agg: [[User]]
proj: [[ThatProject]]
story: https://google.com
dev: 
status: [[grooming]]


```api
v: patch
u: /user/{id}/activate
f:

```

```cm
n: activateUser
f:
- id

```

```ev
n: activatedUser
f:
- id
```

```vw
id: userView
f: 
- id
- active = true
```

```gwt
g: user is authorized
w: user calls api endpoint
t: activatedUser event is saved
a: userView is updated
```


