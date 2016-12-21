---
title: "SetCommonPchSettings | Microsoft Docs"
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
  - "SetCommonPchSettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommonPchSettings メソッド"
ms.assetid: 12f5524b-f654-4222-b979-8ee0d9f58c14
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SetCommonPchSettings
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロジェクトに対してプリコンパイル済みヘッダーを設定します。  
  
## 構文  
  
```  
  
      function SetCommonPchSettings(   
   oProj    
);  
```  
  
#### パラメーター  
 `oProj`  
 選択されたプロジェクト。  
  
## 解説  
 この関数を呼び出して、プロジェクトに対してプリコンパイル済みヘッダーを設定します。  
  
 この関数は、<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A> プロパティを次のいずれかに設定します。  
  
-   **pchUseUsingSpecific** [\/Yu \(プリコンパイル済みヘッダー ファイルの使用\)](../build/reference/yu-use-precompiled-header-file.md) コンパイラ設定を使用します。  
  
-   **pchCreateUsingSpecific** [\/Yc \(プリコンパイル済みヘッダー ファイルの作成\)](../build/reference/yc-create-precompiled-header-file.md) コンパイラ設定を使用します。  
  
## 使用例  
  
```  
if ((strAppType == "LIB" || ((strAppType == "CONSOLE") &&   
   wizard.FindSymbol(SUPPORT_MFC"))) && !Pch)  
   {  
      AddFilesToProject(selProj, strProjectName, InfFile);  
      SetNoCommonPchSettings(selProj);  
   }  
else  
   {  
      AddFilesToProject(selProj, strProjectName, InfFile);  
      SetcommonPchSettings(selProj);  
   }  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [SetNoPchSettings](../ide/setnopchsettings.md)   
 [AddCommonConfig](../ide/addcommonconfig.md)