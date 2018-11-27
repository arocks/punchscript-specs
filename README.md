This repository only maintains the Punchscript language specs

<p align="center"> 
<img width="210" height="298" src="https://raw.githubusercontent.com/arocks/punchscript/master/web/img/logo-full.png">
</p>

Language Reference
------------------

Punchscript is an interpreted scripting language based on punch dialoges of the Indian superstar [Rajninikanth](https://en.m.wikipedia.org/wiki/Rajinikanth). It is an imperative language with infix operators inspired by [ArnoldC](https://github.com/lhartikk/ArnoldC) and [Python](https://www.python.org/). It was developed as a fun exercise and to learn compiler design.

Here are a set of constructs in Punchscript. If you are already familiar with programming then you should be able quickly get up to speed with this.


|Keyword|Equivalent in other languages|Remarks|
|--- |--- |--- |
|`<expr> SOLRAN <var> SEIRAN`|`LET <var> = <expr>`|Assignment statement|
|`MEHHH! <comment>`|`COMMENT <comment>`|Must be at the beginning of a line|
|`NOORU THADAVA SONNA MAADIRI <cond>`<br>`<loop body>`<br>`MAGIZHCHI`|`WHILE <cond>`<br>`<loop body>`<br>`END WHILE`|If the condition evaluates to non-zero then enter loop body|
|`MALAI DA ANNAMALAI <condition>`<br>`<if condition true body>`<br>`EN VAZHI THANI VAZHI`<br>`<else body>`<br>`KATHAM, KATHAM`|`IF <condition>`<br>`<if condition true body>`<br>`ELSE`<br>`<else body>`<br>`END IF`|True means condition evaluates to non-zero. Else part is optional.|
|`IDHU EPADI IRUKU <expr or string>`|`PRINT <expr or string>`|Only place where literal strings (in double quotes) are allowed|
|`I AM CHITTI <ver number>`|`SPEC <ver number>`|Must be first line (lang ver no.) Optional|


#### Syntax

```

<var> = [A-Z a-z][A-Z a-z 0-9 _]*

<expr> = <expr> <op> <expr>

<op> = + - * / % (modulo) > < == <>

```

Keywords: Keywords are in capital letters and may comprise of multiple words.

Variables: All variables are of type Integers. Variable names are case sensitive alphanumeric (including underscores) and starts with alphabet (upper or lowercase).

Expressions: All expressions get evaluated to integers including logical operations. True is represented as 1 and False is 0. For example, 4 > 5 will be evaluated to 0 implying False.

Whitespace: There are no end of line markers like semicolons. So each statement must be on a seperate line. But leading spaces or indentation of a line does not matter.

#### Builtins

Certain variables have special meaning when evaluated

*   BILLA - Generates a different random number (between 0 and MAXINT) when evaluated
*   GURU - Maximum value of integer or MAXINT (currently 55,555)
*   SISHYAN - Minimum value of integer or MININT (currently -MAXINT)

#### Errors

You might get any of these cryptic replies from the language interpreter

|Error Type|What Punchscript Says|
|--- |--- |
|Syntax Error|ENNAMMA KANNU, SOWKIYAMA? <char>|
|Parse Error|THILLU MULLU|
|Runtime Error|KANNA, PANNI DHAN KOOTAMA VARUM... <msg>|
|Divide by zero|DIVIDE BY ZERO? JUJUBE.|

