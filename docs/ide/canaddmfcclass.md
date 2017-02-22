---
title: "CanAddMFCClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddMFCClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddMFCClass メソッド"
ms.assetid: 6a97a410-b028-4aad-9b06-04c12cf481eb
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddMFCClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが MFC クラスをプロジェクトに追加できることを確認するために、ウィザードによって呼び出されます。  
  
## 構文  
  
```  
  
      function CanAddMFCClass(   
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
 クラスを追加できる場合は **true** を返します。MFC プロジェクト以外のプロジェクトや MFC サポートのないプロジェクトに対してユーザーがこの関数を呼び出した場合は **false** を返します。  
  
## 解説  
 実行する予定のコード ウィザードとプロジェクトに互換性があるかどうか、つまりプロジェクトで MFC クラスを使用できるかどうかを確認するために、ウィザードによって呼び出されます。  
  
 PREPROCESS\_FUNCTION パラメーターが[プロジェクト コントロールの .vsz ファイル](../ide/dot-vsz-file-project-control.md)にあると、ウィザードはこの関数を呼び出して、[Visual C\+\+ のコード モデル](http://msdn.microsoft.com/ja-jp/dd6452c2-1054-44a1-b0eb-639a94a1216b) オブジェクトが使用できるかどうかを調べます。  コード モデルが使用できない場合、関数はエラーをレポートし、**false** を返します。  
  
## 使用例  
  
```  
// Determine if an MFC class can be added to the project  
if (CanAddMFCClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [CanAddClass](../ide/canaddclass.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../Topic/IsMFCProject.md)