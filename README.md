# 介绍

ezXML是一个用于解析XML文档的C库，其灵感来自PHP的simpleXML。它是解析XML配置文件或REST web服务响应的理想工具，其运行快速，同时编译量小于20k。

# 示例

```c
int main(int argc, char **argv)
{
    ezxml_t xml;
    char *s;
    int i;

    if (argc != 2) return fprintf(stderr, "usage: %s xmlfile\n", argv[0]);

    xml = ezxml_parse_file(argv[1]);
    printf("%s\n", (s = ezxml_toxml(xml)));
    free(s);
    i = fprintf(stderr, "%s", ezxml_error(xml));
    ezxml_free(xml);
    return (i) ? 1 : 0;
}
```

# 参考链接

http://ezxml.sourceforge.net/