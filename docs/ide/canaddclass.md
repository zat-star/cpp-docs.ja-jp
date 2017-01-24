---
title: "CanAddClass | Microsoft Docs"
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
  - "CanAddClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddClass メソッド"
ms.assetid: 76739742-1e34-470c-910d-8784f0adfbf0
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CanAddClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが実行する予定のコード ウィザードとプロジェクトに互換性があることを確認するために、ウィザードによって呼び出されます。  
  
## 構文  
  
```  
  
      function CanAddClass(   
   oProj,   
   oObject    
);  
```  
  
#### パラメーター  
 `oProj`  
 選択されたプロジェクト。  
  
 `oObject`  
 選択されたオブジェクト。  この場合は、現在のプロジェクトです。  
  
## 戻り値  
 クラスを追加できる場合は **true** を返します。それ以外の場合は **false** を返します。  
  
## 解説  
 PREPROCESS\_FUNCTION パラメーターが[プロジェクト コントロールの .vsz ファイル](../ide/dot-vsz-file-project-control.md)にあると、ウィザードがこの関数を呼び出します。  
  
 この関数では、[Visual C\+\+ のコード モデル](http://msdn.microsoft.com/ja-jp/dd6452c2-1054-44a1-b0eb-639a94a1216b) オブジェクトが使用できるかどうかを確認します。  コード モデルが使用できない場合、関数はエラーをレポートし、**false** を返します。  
  
## 使用例  
  
```  
// Determine if a class can be added to the project  
if (CanAddClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [CanAddMFCClass](../ide/canaddmfcclass.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../Topic/IsMFCProject.md)