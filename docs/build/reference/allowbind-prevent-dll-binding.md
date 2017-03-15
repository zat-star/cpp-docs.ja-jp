---
title: "/ALLOWBIND (DLL をバインドしない) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.PreventDLLBinding"
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWBIND リンカー オプション"
  - "ALLOWBIND リンカー オプション"
  - "-ALLOWBIND リンカー オプション"
  - "バインド (DLL の)"
  - "DLL [C++], 防止 (バインディングを)"
  - "防止 (DLL バインディングを)"
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ALLOWBIND (DLL をバインドしない)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALLOWBIND[:NO]  
```  
  
## 解説  
 \/ALLOWBIND:NO は DLL のヘッダーにビットを設定して、イメージをバインドできないことを Bind.exe に示します。  DLL がデジタル署名されている場合はバインドしないほうがよいでしょう \(バインドによって署名が無効になる\)。  
  
 EDITBIN ユーティリティの [\/ALLOWBIND](../../build/reference/allowbind.md) オプションで、\/ALLOWBIND 機能の既存の DLL を編集できます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **［構成プロパティ］**、**［リンカー］** を展開して、**［コマンド ライン］** をクリックします。  
  
3.  **［追加オプション］** で、`/ALLOWBIND:NO` と入力します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [BindImage 関数](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [BindImageEx 関数](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)