---
title: "/WX (リンカー警告をエラーとして扱う) | Microsoft Docs"
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
  - "/WX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/WX リンカー オプション"
  - "WX リンカー オプション"
  - "-WX リンカー オプション"
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WX (リンカー警告をエラーとして扱う)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/WX[:NO]  
```  
  
## 解説  
 \/WX を指定すると、リンカーが警告を生成する場合に、出力ファイルが生成されません。  
  
 これは、コンパイラの **\/WX** と同様です \(詳細については、「[\/w、\/Wn、\/WX、\/Wall、\/wln、\/wdn、\/wen、\/won \(警告レベル\)](../../build/reference/compiler-option-warning-level.md)」を参照してください\)。  ただし、コンパイルで **\/WX** を指定しても、**\/WX** がリンク フェーズでも有効であると暗黙的に指定されることはありません。各ツールで、**\/WX** を明示的に指定する必要があります。  
  
 既定では、**\/WX** は無効です。  リンカー警告をエラーとして扱うには、**\/WX** を指定します。  **\/WX:NO** は、**\/WX** を指定しないのと同じです。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)