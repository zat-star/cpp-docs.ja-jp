---
title: "CreateSafeName | Microsoft Docs"
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
  - "CreateSafeName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSafeName メソッド"
ms.assetid: 3a0dd4af-776d-4c25-aff9-4c539f173cb8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreateSafeName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ のフレンドリ名を生成します。  
  
## 構文  
  
```  
  
      function CreateSafeName(   
   strName    
);  
```  
  
#### パラメーター  
 `strName`  
 元の名前。  
  
## 戻り値  
 使用できる新規名を返します。  
  
## 解説  
 この関数を呼び出して、C\+\+ では使用できない文字を含む名前から C\+\+ のフレンドリ名を作成します。  この名前には、大文字、小文字、数字、アンダースコア \("\_"\) を使用できます。  
  
 この関数は、元の名前を 1 文字ずつ調べて、使用できない文字を省きます。  元の名前に使用できない文字が含まれている場合は、新しい名前が "My" として返されます。  新しいフレンドリ名の先頭が数字の場合、関数はその名前の前に "My" を付けます。  
  
## 使用例  
  
```  
// Get the project name  
var strProjectName = wizard.FindSymbol("PROJECT_NAME");  
  
// Set the project name to the safe project name.   
var strSafeProjectName = CreateSafeName(strProjectName);  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)