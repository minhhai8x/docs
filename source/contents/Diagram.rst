Diagram
########

1. Install (npm required, please google search about install npm if your mac has no npm)

    .. code-block:: php

        npm install -g mermaid

2. Generate PNG image file from your sequenceDiagram text

    .. code-block:: php

       mermaid -p sequenceDiagram.txt

3. Convention for diagrams

    * http://knsv.github.io/mermaid/sequenceDiagram.html#alt

    * Mấy cái đánh số ①、②、③

        * ① xxxx
        * ② xxxx
        * ③ xxxx
        * ④ xxxx
        * ⑤ xxxx
        * ⑥ xxxx
        * ⑦ xxxx
        * ⑧ xxxx
        * ⑨ xxxx
        * ⑩ xxxx
        * ⑪ xxxx

    * Số ý nghĩa lặp lại số trên

        * ❶
        * ❷
        * ❸
        * ❹
        * ❺
        * ❻
        * ❼
        * ❽
        * ❾

    * Thông thường edit thì có dấu "*" , "+" là add mới và "-" là delete

        * ①* editFunction
        * ②+ newFunction
        * ③- deletedFunction

    * Flow:

    .. image:: ../_static/sequence-convention.gif



