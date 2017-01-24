---
title: "InsertIntoFunction | Microsoft Docs"
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
  - "InsertIntoFunction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InsertIntoFunction メソッド"
ms.assetid: 50500c3c-bee3-4a9c-a403-7dcd752de23c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InsertIntoFunction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[InitInstance](../Topic/CWinApp::InitInstance.md) にコードを挿入するために [AddATLSupportToProject](../ide/addatlsupporttoproject.md) で使用されます。  
  
## 構文  
  
```  
  
      function InsertIntoFunction(   
   oFunction,   
   strSearchString,   
   nStartLine,   
   nEndLine,   
   bInsideIfBlock    
);  
```  
  
#### パラメーター  
 *oFunction*  
 挿入先の関数オブジェクト。  
  
 `strSearchString`  
 挿入箇所を指定するために検索する文字列。  
  
 *nStartLine*  
 [GetCodeForInitInstance](../ide/getcodeforinitinstance.md) に渡す最初の行。  
  
 *nEndLine*  
 [GetCodeForInitInstance](../ide/getcodeforinitinstance.md) に渡す最後の行。  
  
 *bInsideIfBlock*  
 挿入の対象が関数ブロックかどうかを示します。  
  
## 戻り値  
 正常終了した場合は **true** を返します。それ以外の場合は **false** を返します。  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [GetMemberfunction](../Topic/GetMemberfunction.md)