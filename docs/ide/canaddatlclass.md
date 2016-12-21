---
title: "CanAddATLClass | Microsoft Docs"
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
  - "CanAddATLClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddATLClass メソッド"
ms.assetid: 7a8abf90-c1b8-475c-af22-7948478084f9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CanAddATLClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが ATL クラスをプロジェクトに追加できることを確認するために、ウィザードによって呼び出されます。  
  
## 構文  
  
```  
  
      function CanAddATLClass(   
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
 クラスを追加できる場合は **true** を返します。ATL プロジェクト以外のプロジェクトや ATL サポートのないプロジェクトに対してユーザーがこの関数を呼び出した場合は **false** を返します。  
  
## 解説  
 実行する予定のコード ウィザードとプロジェクトに互換性があるかどうか、つまりプロジェクトで ATL クラスを使用できるかどうかを確認するために、ウィザードによって呼び出されます。  
  
 PREPROCESS\_FUNCTION パラメーターが[プロジェクト コントロールの .vsz ファイル](../ide/dot-vsz-file-project-control.md)にあると、ウィザードはこの関数を呼び出して、[Visual C\+\+ のコード モデル](http://msdn.microsoft.com/ja-jp/dd6452c2-1054-44a1-b0eb-639a94a1216b)が使用できるかどうかを調べます。  コード モデルが使用できない場合、関数はエラーをレポートし、**false** を返します。  
  
## 使用例  
  
```  
// Determine if an ATL class can be added to the project  
if (CanAddATLClass(selProj, selObj))  
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
 [IsMFCProject](../Topic/IsMFCProject.md)   
 [CanAddMFCClass](../ide/canaddmfcclass.md)