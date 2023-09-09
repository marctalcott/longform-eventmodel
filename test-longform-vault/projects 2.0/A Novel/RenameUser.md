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
dev: [[Joe]]
status: [[status/dev]]


```api
v: put
u: /user/{id}/name
f:
- fname
- lname
```

```cm
n: renameUser
f:
- id
- fname
- lname

```

```ev
n: renamedUser
f:
- id
- fname
- lname
```

```vw
id: userView
f: 
- id
- fname
- lname
```

```gwt
g: user is authorized
w: user calls api endpoint
t: renamedUser event is saved
a: userView is updated
```


