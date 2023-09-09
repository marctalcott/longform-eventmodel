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
u: /user/{id}/deactivate
f:

```

```cm
n: deactivateUser
f:
- id

```

```ev
n: deactivatedUser
f:
- id
```

```vw
id: userView
f: 
- id
- active = false
```

```gwt
g: user is authorized
w: user calls api endpoint
t: deactivatedUser event is saved
a: userView is updated
```


