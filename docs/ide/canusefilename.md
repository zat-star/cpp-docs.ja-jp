---
title: "CanUseFileName | Microsoft Docs"
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
  - "CanUseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanUseFileName メソッド"
ms.assetid: 60b669fa-9484-4435-b502-78ec8e960a00
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CanUseFileName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ファイルが存在するかどうかを調べます。  ファイルが存在し、そのファイルに制約がない場合、ウィザードはコードをマージして、既存のファイルに追加するかどうかを確認するメッセージを表示します。  
  
## 構文  
  
```  
  
      function CanUseFileName(   
   strFileName,   
   bCheckIfMidlHeader,   
   bCannotExist,   
   bSetMergeFlag    
);  
```  
  
#### パラメーター  
 `strFileName`  
 調べるファイルの名前。  
  
 *bCheckIfMidlHeader*  
 ファイル名が MIDL によって生成されるかどうかを調べる場合は **true**。  
  
 *bCannotExist*  
 ファイル名が既に存在し、上書きできないかどうかを調べる場合は **true**。  
  
 *bSetMergeFlag*  
 ユーザーがコードを既存のファイル名にマージできることを示す MERG\_FILE シンボルを組み込む場合は **true** に設定します。  
  
## 戻り値  
 `strFileName` が一意の場合、または既存のファイルにコードを追加できる場合は **true** を返します。それ以外の場合は **false** を返します。  
  
## 解説  
 この関数を呼び出して、ファイル名が存在するかどうかを調べます。  ファイル名が存在し、そのファイルが MIDL によって作成されていない場合、またはそれ以外の制約がない場合は、ユーザーが新しいコードを既存のファイルにマージできることを示すメッセージが表示されます。  
  
 ファイル名が存在せず、制約もない場合は、指定された名前のファイルが作成されます。  
  
 ファイル名が MIDL によって作成されている場合、またはそれ以外に制約がある場合は、ウィザードによってエラー メッセージが表示されます。  
  
## 使用例  
  
```  
case "HTML_FILE":  
if (!HTML_FILE.disabled)  
   {  
   if (!window.external.FindSymbol("HTML_FILE_VALID"))  
      {  
      bValid = CanUseFileName(obj.value, false, true);  
      if (!bValid)  
      break;  
      window.external.AddSymbol("HTML_FILE_VALID", true)  
      }  
   }  
   bValid = window.external.ValidateFile(HTML_FILE.value, vsCMValidateFileExtHtml);  
   break;   
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)