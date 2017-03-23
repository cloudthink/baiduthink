# match_baidu_semantic
百度和西安交通大核心语义提取大赛


任务设定：

 本次竞赛要求参赛者给出一个算法或模型，从评价性文本片段数据集中，结合上下文提取文本片段中的核心实体，即识别文本片段所讨论最重要的实体。竞赛数据由若干文本片段组成，每个文本片段单独占一行，可能包含多个子句，每个子句以半角句号结尾，要求参赛选手识别出每个文本片段子句及其核心实体。

输入输出说明：

输入：逐行读取文本片段；

输出：逐行输出该文本片段的子句以及提取到的核心实体，以json形式分装，格式如下：

[

 {

        "content": "子句1",

        "core_entity": [

            "entity1",

            "entity2"

        ]

    },

    {

        "content": "子句2",

        "core_entity": [

            "entity1",

            "entity2"

        ]

    }

  ]


#样例数据：

文本片段：
不得不说锤子手机在很多功能操作上的优化真的很用心，尤其是一些看上去并没有什么卵用但让人感觉确实舒服的小设计。

如果说苹果的设计是强行的改变用户习惯，我宁愿选择这个能够随时迁就用户个性的锤子。

答案：
 [

    {

        "content": "不得不说锤子手机在很多功能操作上的优化真的很用心，尤其是一些 看上去并没有什么卵用但让人感觉确实舒服的小设计。",

        "core_entity": [

            "锤子手机"

        ]

    },

    {

        "content": "如果说苹果的设计是强行的改变用户习惯，我宁愿选择这个能够随时 迁就用户个性的锤子。",

        "core_entity": [

            "苹果",

            "锤子"

        ]

    }

]

#评分标准：
正确识别文本片段中至少一个核心实体得1分，如文本片段包含多个核心实体，每多正确识别一个加0.5分，识别错误反扣0.5直到该子句得分为0为止，实体名称以该实体首次出现在文本片段中的名称为准。

----------------------------------------------------------------------------------------------------------------------------------------
#算法思路：详见我的博客：http://blog.csdn.net/datapad
