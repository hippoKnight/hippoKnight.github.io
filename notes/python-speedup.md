# Python Speed

### tags: python, performance

ref: https://wiki.python.org/moin/PythonSpeed/PerformanceTips#Overview:_Optimize_what_needs_optimizing

## notes:
1. 使用 built-in 的 sort 方法, 不好直接用 key 实现时, 可以加个 key 组成 tuple 排序. 自带的 sort 方法是稳定的
2. string concatenation 时, 不要用 + 拼接, 因为 str 是 immutable, + 拼接会生成多个
3. list/dict comprehention 和 map 都比 for loop 快, 因为是 C 实现的
4. dot 要花时间, 可定义局部变量替换
```python
upper = str.upper
newlist = []
append = newlist.append
for word in oldlist:
     append(upper(word))
```
5. 局部变量快过全局变量
上边的代码放入一个方法里会更快 Python accesses local variables much more efficiently than global variables.
```python
def func():
    upper = str.upper
    newlist = []
    append = newlist.append
    for word in oldlist:
        append(upper(word))
```
6. 方法调用/import 均耗时, 根据实际情况安排
7. profiling. 
`import file`

