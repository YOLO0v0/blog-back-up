---
title: Markdown扩展语法
tags:
  - 入门
categories: Markdown
abbrlink: 57876
---
John Gruber的原始设计文档中概述的基本语法主要是为了应付大多数情况下的日常所需元素，但对于某些人来说还不够，这就是扩展语法的用武之地。

一些个人和组织开始通过添加其他元素（例如表，代码块，语法突出显示，URL自动链接和脚注）来扩展基本语法。可以通过使用基于基本Markdown语法的轻量级标记语言，或通过向兼容的Markdown处理器添加扩展来启用这些元素。
<!-- more -->

## Markdown表格

要添加表格，使用三个或多个连字符“---”创建每列的标题，并使用管道符“|"分隔每列。
```
| Syntax........... | Description......... | Test Text........... |
| :---------------: | :------------------: | :------------------: |
| Header            |        Title         |          Here's this |
| Paragraph         |         Text         |             And more |
渲染效果如下：
```
| Syntax........... | Description......... | Test Text........... |
| :---------------: | :------------------: | :------------------: |
|      Header       |        Title         |     Here's this      |
|     Paragraph     |         Text         |       And more       |

### 对齐

在标题行中的连字符的左侧，右侧或两侧添加冒号（:），将列中的文本对齐到左侧，右侧或中心。
```
| Syntax........... | Description......... | Test Text........... |
| :---------------- | :------------------: | -------------------: |
| Header            |        Title         |          Here's this |
| Paragraph         |         Text         |             And more |
渲染效果如下：
```
| Syntax........... | Description......... | Test Text........... |
| :---------------- | :------------------: | -------------------: |
| Header            |        Title         |          Here's this |
| Paragraph         |         Text         |             And more |

### 格式化表格中的文字

您可以在表格中设置文本格式。例如，您可以添加链接，代码（仅反引号（`）中的单词或短语，而不是代码块）和强调。

*您不能添加标题，块引用，列表，水平规则，图像或HTML标签*

### 在表中转义管道字符

您可以使用表格的HTML字符代码（\&#124;）在表中显示竖线（|）字符。

## Markdown 围栏代码块

Markdown基本语法允许您通过将行缩进四个空格或一个制表符来创建代码块。如果发现不方便，请尝试使用受保护的代码块。根据Markdown处理器或编辑器的不同，您将在代码块之前和之后的行上使用三个反引号（(```）或三个波浪号（~~~）。

~~~
```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
渲染效果如下
~~~
```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
### 语法高亮

许多Markdown处理器都支持受围栏代码块的语法突出显示。使用此功能，您可以为编写代码的任何语言添加颜色突出显示。要添加语法突出显示，请在受防护的代码块之前的反引号旁边指定一种语言。
~~~
```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
渲染效果如下
~~~

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
## Markdown 脚注

脚注使您可以添加注释和参考，而不会使文档正文混乱。当您创建脚注时，带有脚注的上标数字会出现在您添加脚注参考的位置。读者可以单击链接以跳至页面底部的脚注内容。

要创建脚注参考，请在方括号（[^1]）内添加插入符号和标识符。标识符可以是数字或单词，但不能包含空格或制表符。标识符仅将脚注参考与脚注本身相关联-在输出中，脚注按顺序编号。

在括号内使用另一个插入符号和数字添加脚注，并用冒号和文本（[^1]: My footnote.）。您不必在文档末尾添加脚注。您可以将它们放在除列表，块引号和表之类的其他元素之外的任何位置。

```
Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.
渲染效果如下
```
Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]:Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.
    



## Markdown 删除线

您可以通过在单词中心放置一条水平线来删除单词。结果看起来~~像这样~~。此功能使您可以指示某些单词是一个错误，要从文档中删除。若要删除单词，请在单词前后使用两个波浪号~~。
```
~~这是一个删除线~~
渲染效果如下
```
~~这是一个删除线~~

## Markdown 任务列表语法

任务列表使您可以创建带有复选框的项目列表。在支持任务列表的Markdown应用程序中，复选框将显示在内容旁边。要创建任务列表，请在任务列表项之前添加破折号-和方括号[ ]，并在[ ]前面加上空格。要选择一个复选框，请在方括号[x]之间添加 x 。
```
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
渲染效果如下
```
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

## 使用表情符号简码

一些Markdown应用程序允许您通过键入表情符号短代码来插入表情符号。这些以冒号开头和结尾，并包含表情符号的名称。
```
去露营了！ :tent: 很快回来。

真好笑！ :joy:
渲染效果如下
```
去露营了！ :tent: 很快回来。

真好笑！ :joy:
Note: 注意：您可以使用此表情[符号简码列表](https://gist.github.com/rxaviers/7360908)，但请记住，表情符号简码因应用程序而异。有关更多信息，请参阅Markdown应用程序的文档
### 附上自己感觉可以用到的以做备份
```
😄 :smile:	😆 :laughing:
😊 :blush:	😃 :smiley:	☺️ :relaxed:
😏 :smirk:	😍 :heart_eyes:	😘 :kissing_heart:
😚 :kissing_closed_eyes:	😳 :flushed:	😌 :relieved:
😆 :satisfied:	😁 :grin:	😉 :wink:
😜 :stuck_out_tongue_winking_eye:	😝 :stuck_out_tongue_closed_eyes:	😀 :grinning:
😗 :kissing:	😙 :kissing_smiling_eyes:	😛 :stuck_out_tongue:
😴 :sleeping:	😟 :worried:	😦 :frowning:
😧 :anguished:	😮 :open_mouth:	😬 :grimacing:
😕 :confused:	😯 :hushed:	😑 :expressionless:
😒 :unamused:	😅 :sweat_smile:	😓 :sweat:
😥 :disappointed_relieved:	😩 :weary:	😔 :pensive:
😞 :disappointed:	😖 :confounded:	😨 :fearful:
😰 :cold_sweat:	😣 :persevere:	😢 :cry:
😭 :sob:	😂 :joy:	😲 :astonished:
😱 :scream:	:neckbeard: :neckbeard:	😫 :tired_face:
😠 :angry:	😡 :rage:	😤 :triumph:
😪 :sleepy:	😋 :yum:	😷 :mask:
😎 :sunglasses:	😵 :dizzy_face:	👿 :imp:
😈 :smiling_imp:	😐 :neutral_face:	😶 :no_mouth:
💔 :broken_heart:    ❤️ :heart:
💩 :shit:	👍 :+1:	👍 :thumbsup:
👎 :-1:	👎 :thumbsdown:	👌 :ok_hand:
👊 :punch:	👊 :facepunch:	✊ :fist:
✌️ :v:	👋 :wave:	✋ :hand:
✋ :raised_hand:	👐 :open_hands:	☝️ :point_up:
👇 :point_down:	👈 :point_left:	👉 :point_right:
🙌 :raised_hands:	🙏 :pray:	👆 :point_up_2:
👏 :clap:	💪 :muscle:	🤘 :metal:
🖕 :fu:    💏 :couplekiss:    	💬 :speech_balloon:
🐱 :cat:	🐶 :dog:	🐭 :mouse:
🐹 :hamster:	🐰 :rabbit:	🐺 :wolf:
🐸 :frog:	🐯 :tiger:	🐨 :koala:
🐻 :bear:	🐷 :pig:	🐽 :pig_nose:
🐮 :cow:	🐗 :boar:	🐵 :monkey_face:
🐒 :monkey:	🐴 :horse:	🐎 :racehorse:
🐫 :camel:	🐑 :sheep:	🐘 :elephant:
🐼 :panda_face:	🐍 :snake:	🐦 :bird:
🐤 :baby_chick:	🐥 :hatched_chick:	🐣 :hatching_chick:
🐔 :chicken:	🐧 :penguin:	🐢 :turtle:
🐛 :bug:	🐝 :honeybee:	🐜 :ant:
🪲 :beetle:	🐌 :snail:	🐙 :octopus:
🐠 :tropical_fish:	🐟 :fish:	🐳 :whale:
🐋 :whale2:	🐬 :dolphin:	🐄 :cow2:
🐏 :ram:	🐀 :rat:	🐃 :water_buffalo:
🐅 :tiger2:	🐇 :rabbit2:	🐉 :dragon:
🐐 :goat:	🐓 :rooster:	🐕 :dog2:
🐖 :pig2:	🐁 :mouse2:	🐂 :ox:
🐲 :dragon_face:	🐡 :blowfish:	🐊 :crocodile:
🐪 :dromedary_camel:	🐆 :leopard:	🐈 :cat2:
🐩 :poodle:	🐾 :paw_prints:	💐 :bouquet:
🌸 :cherry_blossom:	🌷 :tulip:	🍀 :four_leaf_clover:
🌹 :rose:	🌻 :sunflower:	🌺 :hibiscus:
🍁 :maple_leaf:	🍃 :leaves:	🍂 :fallen_leaf:
🌿 :herb:	🍄 :mushroom:	🌵 :cactus:
🌴 :palm_tree:	🌲 :evergreen_tree:	🌳 :deciduous_tree:
🌰 :chestnut:	🌱 :seedling:	🌼 :blossom:
🌾 :ear_of_rice:
内容不全详情请参考上述符号简码列表链接

```
## 自动网址链接
许多Markdown处理器会自动将URL转换为链接。这意味着如果您输入http://www.example.com，即使您未使用方括号，您的Markdown处理器也会自动将其转换为链接。
```
http://www.example.com
如下所示
```
http://www.example.com

### 禁用自动URL链接

如果您不希望自动链接URL，则可以通过将URL表示为带反引号的代码来删除该链接。

~~~
`http://www.example.com`
渲染效果如下
~~~
`http://www.example.com`
















