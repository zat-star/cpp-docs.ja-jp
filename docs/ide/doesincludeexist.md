---
title: "DoesIncludeExist | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoesIncludeExist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoesIncludeExist メソッド"
ms.assetid: 39751a3d-dfe5-423c-bd94-a53771c3e360
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DoesIncludeExist
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定のヘッダー ファイルに対する `#include` ステートメントがファイルにあるかどうかを示します。  
  
## 構文  
  
```  
  
      function DoesIncludeExist(   
   oProj,   
   strHeaderFile,   
   strInsertIntoFile    
);  
```  
  
#### パラメーター  
 `oProj`  
 選択されたプロジェクト。  
  
 *strHeaderFile*  
 検索するヘッダー ファイルの名前。  
  
 `strInsertIntoFile`  
 ヘッダー ファイルに対する `#include` ステートメントを含むソース ファイル。パスは指定しません。  
  
## 戻り値  
 指定のヘッダー ファイルがインクルードされている場合は **true** を返します。それ以外の場合は **false** を返します。  
  
## 解説  
 特定のヘッダー ファイルに対する `#include` が `strInsertIntoFile` で指定されたファイルにあるかどうかを示します。  
  
## 使用例  
  
```  
// Check to see if #include for atlbase.h   
// is included in the project's stdafx.h.  
// and add it if it is not.  
if (!DoesIncludeExist(selProj, "<atlbase.h>", strSTDAFX))  
   oCM.AddInclude("<atlbase.h>", strSTDAFX, vsCMAddPositionEnd);  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)