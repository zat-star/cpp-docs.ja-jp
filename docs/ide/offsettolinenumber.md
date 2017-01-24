---
title: "OffsetToLineNumber | Microsoft Docs"
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
  - "OffsetToLineNumber"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OffsetToLineNumber 関数"
ms.assetid: ac7e3c22-6b3b-432c-85cc-b50bbef9ce8c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OffsetToLineNumber
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数本体のインデックスを行番号に変換するために [InsertIntoFunction](../ide/insertintofunction.md) によって呼び出されます。  
  
## 構文  
  
```  
  
      function OffsetToLineNumber(   
   strString,   
   nPos    
);  
```  
  
#### パラメーター  
 `strString`  
 関数本体を含む文字列。  関数本体は複数行から成る文字列であり、その各行は CR\-LF \(キャリッジ リターンとラインフィード\) 文字のペアで区切られています。  
  
 `nPos`  
 文字列内の位置。  
  
## 戻り値  
 `nPos` が示す関数本体の行を返します。  関数の最初の行は、行 1 です \(行 0 ではありません\)。  
  
## 解説  
 関数本体の指定位置の行番号を調べます。  
  
 この関数は、関数本体の `nPos` で指定されたインデックスを行番号に変換するために `InsertIntoFunction` によって呼び出されます。  
  
## 使用例  
  
```  
strString = "function DelFile(fso,  
 strWizTempFile)\r\n{\r\n\ttry\r\n\t{\r\nif   
(fso.FileExists(strWizTempFile))\r\nreturn true;\r\n";  
  
nLine =  OffsetToLineNumber(strString, 60);  
  
// The return value for the above is 5, because character 60 in the string   
// occurs in the 5th line within the string.  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [LineBeginsWith](../ide/linebeginswith.md)