---
title: "LineBeginsWith | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LineBeginsWith"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LineBeginsWith メソッド"
ms.assetid: cbdd08ad-7309-4504-9f23-1c22bb3e4bd0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# LineBeginsWith
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した文字列が行頭にあるかどうかを判断するために [InsertIntoFunction](../ide/insertintofunction.md) によって呼び出されます。  
  
## 構文  
  
```  
  
      function LineBeginsWith(   
   strBody,   
   strSearchString,   
   nStartPos    
);  
```  
  
#### パラメーター  
 *strBody*  
 関数の本体。  
  
 `strSearchString`  
 検索する文字列。  
  
 *nStartPos*  
 検索の開始位置。  
  
## 戻り値  
 文字列が検出された場合は **true** を返します。それ以外の場合は **false** を返します。  
  
## 解説  
 この関数は、指定した文字列が行頭にあるかどうかを判断するために `InsertIntoFunction` によって呼び出されます。  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [OffsetToLineNumber](../ide/offsettolinenumber.md)