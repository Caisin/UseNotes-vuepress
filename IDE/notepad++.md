# Notepad++

## 正则表达式
> `$` 表示行末
>
> `.*关键字.*\r\n` 指定关键字的行
>
> `^(.*?)$\s+?^(?=.*^\1$)` 重复行
>
> 关键字之后（包含关键字本身）的所有字符
>> `(关键字)(.*?$)`
>>
>> `关键字.*$`
>>
>> `(关键字)([^关键字]*$)`
>
> 关键字之前（包含关键字本身）的所有字符
>> `^([^关键字]*)关键字`
>>
>> `^.*关键字`
>>
>> `(^.*?)关键字`
>
> `(^.*?关键字.*?)关键字` 每行中的第二个关键字之前（包含关键字本身）的所有字符
>
> `关键字$`行末的关键字
>
> 查找目标`^[^\n]*\n([^\n]*)` 替换为`\1`  隔行删除
> 
>