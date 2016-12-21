---
title: "SetMergeProxySymbol | Microsoft Docs"
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
  - "SetMergeProxySymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetMergeProxySymbol メソッド"
ms.assetid: d6a9db59-2d5b-4431-98bc-785675e0eafe
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SetMergeProxySymbol
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この関数は、\_MERGE\_PROXYSTUB シンボルを追加するために、必要に応じてウィザードによって呼び出されます。  
  
## 構文  
  
```  
  
      function SetMergeProxySymbol(   
   oProj    
);  
```  
  
#### パラメーター  
 `oProj`  
 選択されたプロジェクト オブジェクト。  
  
## 解説  
 この関数は、\_MERGE\_PROXYSTUB シンボルを追加するために、必要に応じてウィザードによって呼び出されます。  
  
## 使用例  
  
```  
SetMergeProxySymbol (selproj);  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)