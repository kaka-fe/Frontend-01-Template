# 重学HTML

HTML的定义: XML与SGML

    [dtd](https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd)
    [XHTML namespace](https://www.w3.org/1999/xhtml/)

## HTML标签--语义

## 标签引用
    &amp;
    &lt;
    &quot;

## NODE

- Element

### 操作
**living list**
- parentNode
- childNodes
- firstChild
- lastChild
- nextSibling
- previousSibling
### 修改

__node不能同时插入在多个地方, 即二次插入时，先在目前位置remove, 再insert__
- appendChild
- insertBerfore
- removeChild
- replaceChild

### 高级操作
- compareDocumentPosition 比较两个节点参数的函数
- contains 检查包含关系
- isEqualNode 两个节点结构是否相同
- isSameNode 相对于===
- cloneNode 复制节点，参数为true时，深拷贝

## Event

