---
title: "SetErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetErrorInfo メソッド"
ms.assetid: 78bca763-3f90-4e04-b566-b4b7fe2431b1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# SetErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在のエラー情報を提供するために、[OnWizFinish](../Topic/OnWizFinish.md) と [CanUseFileName](../ide/canusefilename.md) によって呼び出されます。  
  
## 構文  
  
```  
  
      function SetErrorInfo(   
   oErrorObj   
);  
```  
  
#### パラメーター  
 *oErrorObj*  
 エラー オブジェクト。  
  
## 解説  
 現在のエラー情報を提供するために、[OnWizFinish](../Topic/OnWizFinish.md) と [CanUseFileName](../ide/canusefilename.md) によって呼び出されます。  詳細については、「Visual C\+\+ ウィザード モデル」のドキュメントの「<xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.SetErrorInfo%2A>」を参照してください。  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)