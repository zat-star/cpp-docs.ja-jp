---
title: "GetMaxID | Microsoft Docs"
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
  - "GetMaxID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMaxID メソッド"
ms.assetid: a155ec2e-6132-4e40-9b85-d710538778a1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetMaxID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このインターフェイスとそのすべての基本インターフェイスのメンバーのうち、最上位の `dispid` を取得します。  
  
## 構文  
  
```  
  
      function GetMaxID(   
   ointerface    
);  
```  
  
#### パラメーター  
 *ointerface*  
 <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface> オブジェクト。  
  
## 戻り値  
 *oInterface* とそのすべての基本インターフェイスのメンバーのうち、最上位の dispid を返します。  
  
## 解説  
 この関数を呼び出して、指定のインターフェイスとそのすべての基本インターフェイスのメンバーのうち、最上位の dispid を取得します。  
  
## 使用例  
  
```  
if (strInterfaceType == "custom")  
      window.external.AddSymbol("DISPID_DISABLED", true);  
   else  
   {  
      var nDispID = window.external.FindSymbol("DISPID");  
      if (!nDispID.length)  
      {  
         nDispID = GetMaxID(oInterface) + 1;  
         window.external.AddSymbol("DISPID", nDispID);  
      }  
   }  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)