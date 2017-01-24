---
title: "IncludeCodeElementDeclaration | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IncludeCodeElementDeclaration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IncludeCodeElementDeclaration メソッド"
ms.assetid: 714e76e4-76bc-439a-982a-cf9d4ada7677
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IncludeCodeElementDeclaration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`strInFile` に include ステートメントを追加し、`strCodeElemName` を実装しているヘッダーをインクルードします。この処理は、そのようなヘッダーが `oProj` で検出された場合に行われます。  
  
## 構文  
  
```  
  
      function IncludeCodeElementDeclaration(   
   oProj,   
   strCodeElemName,   
   strInFile    
);  
```  
  
#### パラメーター  
 `oProj`  
 選択されたプロジェクト。  
  
 `strCodeElemName`  
 定義ヘッダーの検索を行うコード要素の完全な名前。  
  
 `strInFile`  
 定義ヘッダーが検出された場合に、定義ヘッダーを組み込むファイル。  
  
## 解説  
 `strInFile` にinclude ステートメントを追加し、`strCodeElemName` を実装しているヘッダーをインクルードします。この処理は、そのようなヘッダーが `oProj` で検出された場合に行われます。  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)