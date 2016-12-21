---
title: "/WINMDDELAYSIGN (winmd の部分署名) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.WINMDDelaySign"
dev_langs: 
  - "C++"
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WINMDDELAYSIGN (winmd の部分署名)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルに公開キーを挿入することによって、Windows ランタイム メタデータ \(.winmd\) ファイルの部分署名を有効にします。  
  
```  
  
/WINMDDELAYSIGN[:NO]  
  
```  
  
## 解説  
 .winmd ファイルに適用される [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) リンカー オプションに似ています。  .winmd ファイルに公開キーだけを含める場合は、**\/WINMDDELAYSIGN** を使用します。  **\/WINMDDELAYSIGN:NO** が指定されている既定で、リンカーは機能します; つまり、winmd ファイルに署名されません。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[Windows メタデータ\]** プロパティ ページを選択します。  
  
4.  **\[Windows メタデータ遅延署名\]** ドロップダウン リスト ボックスで、目的のオプションを選択します。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)