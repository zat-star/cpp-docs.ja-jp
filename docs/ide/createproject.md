---
title: "CreateProject | Microsoft Docs"
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
  - "CreateProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateProject メソッド"
ms.assetid: b5598b46-fe29-4ad0-8bfe-a4dc789aeebd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreateProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ プロジェクトを作成します。  
  
## 構文  
  
```  
  
      function CreateProject(   
   strProjectName,   
   strProjectPath    
);  
```  
  
#### パラメーター  
 `strProjectName`  
 プロジェクト名を含む文字列。  
  
 *strProjectPath*  
 プロジェクトのパスを含む文字列。  
  
## 戻り値  
 プロジェクト オブジェクトです。  
  
## 解説  
 この関数を呼び出して、Visual Studio で開くことができる C\+\+ プロジェクトを作成します。  ウィザードのコンテキスト パラメーター **WizardType** が **vsWizardAddSubProject** に指定されている場合、プロジェクトはサブプロジェクトとして既存のプロジェクトに追加されます。  詳細については、「[ContextParams 列挙型](../Topic/Context%20Parameters%20for%20Launching%20Wizards.md)」を参照してください。  
  
## 使用例  
 「[AddFilesToProject](../Topic/AddFilesToProject.md)」を参照してください。  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)