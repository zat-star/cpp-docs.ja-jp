---
title: "/FORCE (ターゲットを強制的に出力) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ForceLink"
  - "/force"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FORCE リンカー オプション"
  - "ファイル出力 (リンカーの)"
  - "FORCE リンカー オプション"
  - "-FORCE リンカー オプション"
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FORCE (ターゲットを強制的に出力)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## 解説  
 \/FORCE オプションを使用すると、未定義のシンボルが参照された場合や、シンボルが複数回定義された場合でも、有効な .exe ファイルまたは DLL ファイルが強制的に生成されます。  
  
 \/FORCE オプションは、次の引数 \(省略可能\) を使用します。  
  
-   \/FORCE:MULTIPLE と指定すると、シンボルの定義が重複していても出力ファイルが作成されます。  
  
-   \/FORCE:UNRESOLVED と指定すると、未定義のシンボルがあっても出力ファイルが作成されます。\/FORCE:UNRESOLVED は、エントリ ポイントのシンボルが未解決の場合は無視されます。  
  
 \/FORCE に引数を指定しないと、MULTIPLE と UNRESOLVED の両方の引数が暗黙に指定されます。  
  
 このオプションを設定して生成したファイルは、正常に動作しないことがあります。  \/FORCE オプションを設定すると、インクリメンタル リンクが行われなくなります。  
  
 モジュールが **\/clr** を指定してコンパイルされている場合、**\/FORCE** ではイメージは作成されません。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)