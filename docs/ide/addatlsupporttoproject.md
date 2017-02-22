---
title: "AddATLSupportToProject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddATLSupportToProject メソッド"
ms.assetid: 26708f22-1e9b-4432-83b2-ed94c765b753
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# AddATLSupportToProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC プロジェクトに ATL サポートを追加します。  
  
## 構文  
  
```  
  
      function AddATLSupportToProject(   
   oProj   
);  
```  
  
#### パラメーター  
 `oProj`  
 選択されたプロジェクト。  
  
## 戻り値  
 ATL サポートが MFC プロジェクトに正常に追加された場合は **true** を返します。  
  
## 解説  
 この関数を使用して、ウィザードが作成した MFC プロジェクトに ATL サポートを追加します。  
  
 ウィザードでは、ATL サポートを MFC プロジェクトに追加するかどうかを確認するメッセージ ボックスが表示されます。  追加を指定すると、ウィザードでは、作成された MFC プロジェクトが ATL をサポートするように、既存のサポートを調べて、必要な GUID、テンプレート、ヘッダー、および機能をすべて追加します。  
  
## 使用例  
  
```  
var oCM = selProj.CodeModel;  
var L_TRANSACTION_Text = "Add ATL Support To Project";  
oCM.StartTransaction(L_TRANSACTION_Text);  
var bRet = AddATLSupportToProject(selProj);  
if (bRet)  
   oCM.CommitTransaction();  
else  
   oCM.AbortTransaction();  
return bRet;  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../Topic/IsMFCProject.md)   
 [ATL の概要](../Topic/Introduction%20to%20ATL.md)