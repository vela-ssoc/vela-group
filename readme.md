# group
> 用户组获取
 
#### 组字段
- name &emsp;&emsp;名称
- gid  &emsp;&emsp;id

#### 扩展方法
- [vela.group.all(cnd)](#####全部组) &emsp;&emsp;&emsp;获取组
- [vela.group.snapshot()](#####组快照) &emsp;&emsp;&emsp;获取组快照

##### 全部组
> []v = vela.group.all(cnd) 返回Slice
```lua
    local v = vela.group.all()
    local v = vela.group.all("name = root")

    for i=1,v.size do
       print(v[i]) 
    end 
```

#### 组快照
> v = vela.group.snapshot()
```lua
    local s = vela.group.snapshot()
    s.sync()
    v.on_delete(function(group) end)
    v.on_create(function(group) end)
    v.on_update(function(group) end)
    v.poll(4)
```
