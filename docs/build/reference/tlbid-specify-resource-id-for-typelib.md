---
title: "/TLBID (タイプ ライブラリのリソース ID の指定) | Microsoft Docs"
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
  - "/tlbid"
  - "VC.Project.VCLinkerTool.TypeLibraryResourceID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".tlb ファイル, 指定 (リソース ID を)"
  - "/TLBID リンカー オプション"
  - "tlb ファイル, 指定 (リソース ID を)"
  - "TLBID リンカー オプション"
  - "-TLBID リンカー オプション"
  - "タイプ ライブラリ, 指定 (リソース ID を)"
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLBID (タイプ ライブラリのリソース ID の指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBID:id  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 `id`  
 リンカーによって作成されたタイプ ライブラリに対してユーザーが指定した値。  リソース ID の既定値 1 をオーバーライドします。  
  
## 解説  
 属性を使用するプログラムをコンパイルすると、タイプ ライブラリが作成されます。  リンカーがタイプ ライブラリに割り当てるリソース ID は 1 です。  
  
 リンカーによって割り当てられたリソース ID が既存のリソースと競合する場合は、\/TLBID を使って別の ID を指定できます。  `id` に渡すことができる値の範囲は 1 ～ 65535 です。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[埋め込み IDL\]プロパティ ページをクリックします。  
  
4.  \[タイプ ライブラリのリソース ID\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)