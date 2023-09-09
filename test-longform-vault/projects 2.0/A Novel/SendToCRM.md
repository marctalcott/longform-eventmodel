
## meta:
agg: [[User]]
proj: [[ThatProject]]
story: https://google.com
dev: 
status: [[grooming]]
trigger: [[AddUser#AddedUser]]


```wfe
ev: ![[AddUser#AddedUser]]
```

```

```api
v: post
u: /user/{id}/SendToCRM
f:

```

```cm
n: sendUserToCRM
f:
- id

```

```ev
n: sentUserToCRM
f:
- id
```

```vw
id: userView
f: 
- id
- sendUserToCRMDateTime = utc
```

```gwt
g: user is authorized
w: user calls api endpoint
t: user is sent to CRM
a: sentUserToCRM event is saved
a: userView is updated with time stamp
```


