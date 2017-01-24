---
title: "HTML ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "カスタム ウィザード, HTML ファイル"
  - "カスタム ウィザード, ユーザー インターフェイス"
  - "ファイル [C++], 作成 (カスタム ウィザードで)"
  - "HTML ページ, ユーザー インターフェイス (カスタム ウィザードの)"
  - "ユーザー インターフェイス (ウィザードの)"
  - "ウィザード [C++], ユーザー インターフェイス (カスタム ウィザードの)"
ms.assetid: 3b6ed080-6560-418b-b908-d84d71bdf145
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HTML ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィザードには、ユーザー インターフェイス \(UI: User Interface\)、つまり HTML インターフェイスを含めることができます。  ウィザードには、Default.htm の他に .htm ファイルを必要なだけ含めることができます。この設定は、[カスタム ウィザード](../ide/custom-wizard.md)の **\[ページ数\]** ボックスで行うことができます。  各 .htm ファイルはウィザードの HTML ページを表します。HTML ページには、\[次へ\] ボタンと \[戻る\] ボタン、タブ、またはウィザードのデザインで指定するその他の任意の形式を使用してアクセスできます。  
  
 HTML ファイルの内容は次のとおりです。  
  
-   SYMBOL タグ。このタグは、ユーザー定義オプションの既定値を指定します。  ユーザーが \[完了\] をクリックすると、シンボルが次のようにシンボル テーブルに書き込まれます。  
  
```  
<SYMBOL NAME='HEADER_FILE' VALUE='MyHeader.h' TYPE=text></SYMBOL>  
```  
  
 このウィザードのユーザー インターフェイスでは、シンボル テーブルで "HEADER\_FILE" と指定されたテキスト ボックスに、既定のテキスト "MyHeader.h" が含まれます。  ウィザードの UI でこの値を変更できます。変更された値は、\[完了\] をクリックしたときに、プロジェクトのシンボル テーブルに次のように書き込まれます。  
  
```  
<SYMBOL NAME='CHECKBOX1' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
 ウィザードの UI では、シンボル テーブルで "CHECKBOX1" と指定されたチェック ボックスは既定でオフになります。  HTML の UI でこのボックスをオンにできます。変更された値は、\[完了\] をクリックしたときに、シンボル テーブルに書き込まれます。  
  
 各 .htm ファイルによって、ユーザーの選択項目がシンボル テーブルに記録されます。  
  
-   [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) のインクルード。このファイルには、一般的に使用される便利な JScript 関数、および Default.js が含まれます。  
  
-   HTML で表示される、プロジェクトのイメージへの参照。  
  
-   HTML テキストと書式指定。ウィザードのユーザー インターフェイスの外観をカスタマイズします。  
  
-   JScript 関数。これらの関数は、Visual C\+\+ のウィザード オブジェクト モデルにアクセスして、ウィザード内から動作をカスタマイズします。  これらの関数は、次の例に示すように、HTML ページの \<SCRIPT LANGUAGE\='JSCRIPT'\> セクションに指定されています。  
  
    > [!NOTE]
    >  HTML からウィザード オブジェクト モデルおよび環境オブジェクト モデルにアクセスするには、オブジェクト モデルのアイテムの前に "window.external" を付けます。  
  
    ```  
    function InitDocument(document)  
    {  
       setDirection();  
  
       if (window.external.FindSymbol('DOCUMENT_FIRST_LOAD'))  
       {  
          // This function sets the default symbols based   
          // on the values specified in the SYMBOL tags above  
          //  
          window.external.SetDefaults(document);  
       }  
  
       // Load the document and initialize the controls   
       // with the appropriate symbol values  
       //  
       window.external.Load(document);  
    }  
    ```  
  
 コンソール アプリケーション ウィザードのサンプルを次に示します。  
  
```  
<SYMBOL NAME='WIZARD_DIALOG_TITLE' TYPE=text VALUE='Console Application Wizard'></SYMBOL>  
  
<SYMBOL NAME='EMPTY_PROJECT' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_ATL' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_MFC' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
## 参照  
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)