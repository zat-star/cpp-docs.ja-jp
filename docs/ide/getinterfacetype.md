---
title: "GetInterfaceType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetInterfaceType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfaceType メソッド"
ms.assetid: cc6403a8-0c2b-47f7-a8f7-9db95df87d5a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetInterfaceType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターフェイスの種類を取得します。  
  
## 構文  
  
```  
  
      function GetInterfaceType(   
   oInterface    
);  
```  
  
#### パラメーター  
 *oInterface*  
 <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface> オブジェクト。  
  
## 戻り値  
 カスタム、デュアル、ディスパッチ、OLE オートメーションなどのインターフェイスの種類を示す文字列を返します。  
  
## 解説  
 この関数を呼び出して、インターフェイスの種類を取得します。  
  
## 使用例  
 「[GetMaxID](../ide/getmaxid.md)」を参照してください。  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [GetInterfaceClasses](../Topic/GetInterfaceClasses.md)