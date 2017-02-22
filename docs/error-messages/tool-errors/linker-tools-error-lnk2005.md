---
title: "リンカ ツール エラー LNK2005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2005"
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# リンカ ツール エラー LNK2005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbol は既に object で定義されています。  
  
 指定された `symbol` \(修飾された形式で表示\) は重複定義されています。  
  
 詳細については、次のサポート技術情報の文書を参照してください。  
  
-   「LNK2005 Errors When Link C Run\-Time Libraries Are Linked Before MFC Libraries \(Q148652\)」  
  
-   「Global Overloaded Delete Operator Causes LNK2005 \(Q140440\)」  
  
-   「LNK2005 Errors on New and Delete When Defining \_ATL\_MIN\_CRT \(Q184235\)」  
  
 サポート技術情報の文書は、MSDN ライブラリ CD\-ROM または [http:\/\/support.microsoft.com\/search](http://support.microsoft.com/search) で参照できます。  
  
 このエラーの後に、致命的なエラー [LNK1169](../Topic/Linker%20Tools%20Error%20LNK1169.md) が発生します。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) も使用しているときに、スタティック ライブラリとダイナミック ライブラリが混在しています。  
  
2.  symbol は、\([\/Gy](../../build/reference/gy-enable-function-level-linking.md) でコンパイルすることによって作成された\) パッケージ化された関数であり、複数のファイルに含まれていますが、コンパイルとコンパイルの間で変更されました。  `symbol` を含むすべてのファイルを再コンパイルします。  
  
3.  symbol は、異なるライブラリの 2 つのメンバー オブジェクトで異なる定義がされており、両方のメンバー オブジェクトが使用されました。  
  
4.  絶対定義が 2 回行われ、それぞれの定義で値が異なります。  
  
5.  ヘッダー ファイルで変数が宣言および定義されました。  次の解決策が考えられます。  
  
    -   変数を .h で `extern BOOL MyBool;` と宣言し、.c または .cpp ファイルで `BOOL MyBool = FALSE;` と代入します。  
  
    -   変数を [static](../../misc/static-cpp.md) で宣言します。  
  
    -   変数を [selectany](../../cpp/selectany.md) で宣言します。  
  
6.  uuid.lib を GUID \(oledb.lib や adsiid.lib など\) を定義する他の .lib ファイルと組み合わせて使用する場合。  次に例を示します。  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     修正するには、リンカーのコマンド ライン オプションに [\/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md) を追加し、uuid.lib が最初に参照されるライブラリであることを確認します。