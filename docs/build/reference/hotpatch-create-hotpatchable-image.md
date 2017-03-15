---
title: "/hotpatch (ホットパッチ可能なイメージの作成) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/hotpatch"
  - "VC.Project.VCCLCompilerTool.CreateHotpatchableImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ホット パッチ"
  - "-hotpatch コンパイラ オプション [C++]"
  - "/hotpatch コンパイラ オプション [C++]"
  - "ホット パッチ"
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# /hotpatch (ホットパッチ可能なイメージの作成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イメージをホットパッチできるようにします。  
  
## 構文  
  
```  
/hotpatch  
```  
  
## 解説  
 コンパイルで **\/hotpatch** を使用する場合、コンパイラは、各関数の最初の命令が、ホットパッチに必要な 2 バイト以上であることを確認します。  
  
 イメージのホットパッチを可能にするための準備を完了するには、**\/hotpatch** を使用してコンパイルした後に、[\/FUNCTIONPADMIN \(ホットパッチ可能なイメージの作成\)](../../build/reference/functionpadmin-create-hotpatchable-image.md) を使用してリンクさせる必要があります。  イメージをコンパイルして単一の cl.exe 呼び出しにリンクすると、**\/hotpatch** は暗黙的に **\/functionpadmin** を指定します。  
  
 ARM アーキテクチャでは命令は常に 2 バイト以上であるため、また、x64 コンパイルは常に **\/hotpatch** が指定されているように扱われるため、これらのターゲットのコンパイル時に **\/hotpatch** を指定する必要はありません。ただし、それらのホットパッチ可能なイメージを作成するために **\/functionpadmin** を使用してリンクさせる必要はあります。  **\/hotpatch** コンパイラ オプションは、x86 コンパイルのみに影響を与えます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加オプション\]** ボックスにコンパイラ オプションを追加します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## ガイダンス  
 更新管理の詳細については、「Security Guidance for Update Management \(更新管理のセキュリティ ガイダンス\)」\([http:\/\/www.microsoft.com\/technet\/security\/guidance\/PatchManagement.mspx](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx)\) を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)