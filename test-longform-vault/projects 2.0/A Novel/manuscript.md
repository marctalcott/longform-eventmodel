# AddUser


## meta:
agg: User
proj: ThatProject
story: https://google.com
dev: Joe
status: status/dev


```cm
n: adduser
f:
- id
- fname
- lname

```

## AddedUser
```ev
n: addeduser
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
g: 
w:
t:
```

```story
As a AppUser, I want to add a User to the system, so I can manage their account info.



```

---

# RenameUser



## meta:
agg: User
proj: ThatProject
story: https://google.com
dev: Joe
status: status/dev


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




---

# ActivateUser



## meta:
agg: User
proj: ThatProject
story: https://google.com
dev: 
status: grooming


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




---

# DeactivateUser



## meta:
agg: User
proj: ThatProject
story: https://google.com
dev: 
status: grooming


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




---

# SendToCRM


## meta:
agg: User
proj: ThatProject
story: https://google.com
dev: 
status: grooming
trigger: AddUser#AddedUser


```wfe
ev: !AddUser#AddedUser
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


