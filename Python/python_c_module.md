#  Python扩展


**扩展的定义：**一般来说，所有能被整合或导入到其他python脚本的代码，都可以称为扩展。



**为什么要扩展：**

- 添加/额外的（非python）功能
- 性能瓶颈的效率提升
- 保持专有源代码私密

**创建Python扩展**

- 创建应用程序代码
- 利用样板来包装代码
- 编译与测试


<table>
><tr>
<td>函 数</td>
><td>描 述</td>
</tr>
><tr>
<td>Python到c</td>
><td></td>
</tr>
>><tr>
<td>int PyArgTuple()</td>
><td>把Python传过来的参数转为c</td>
</tr>
></tr>
>><tr>
<td>c到python</td>
><td></td>
</tr>
>>><tr>
<td>PyObject* Py_BuildValue()</td>
><td>把c的数据转为Python的一个或一组对象，然后返回</td>
</tr>
></table>

**Python和c之间的数据转换的通用代码**


<table>
<tr>
<td>格式代码</td>
<td>Python类型</td>
<td>c类型</td>
</tr>
<tr>
<td>s</td>
<td>str</td>
<td>char指针</td>
</tr>
<tr>
<td>i</td>
<td>int</td>
<td>int</td>
</tr>
<tr>
<td>l</td>
<td>long</td>
<td>long</td>
</tr>
<tr>
<td>c</td>
<td>str</td>
<td>char</td>
</tr>
<tr>
<td>d</td>
<td>float</td>
<td>double</td>
</tr>
</table>