
## meta:
agg: [[User]]
proj: [[ThatProject]]
story: https://google.com
dev: [[Joe]]
status: [[status/dev]]


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