---
title: "/DEFAULTLIB (既定のライブラリの指定) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.DefaultLibraries"
  - "/defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEFAULTLIB リンカー オプション"
  - "DEFAULTLIB リンカー オプション"
  - "-DEFAULTLIB リンカー オプション"
  - "ライブラリ, 追加 (一覧に)"
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEFAULTLIB (既定のライブラリの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEFAULTLIB:library  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *library*  
 外部参照を解決するときに検索するライブラリの名前。  
  
## 解説  
 \/DEFAULTLIB オプションでは、LINK が参照を解決するときに検索するライブラリを引数 *library* で指定します。  まず、コマンド ラインで指定したライブラリが検索され、次に \/DEFAULTLIB オプションで指定したライブラリが検索され、最後に .obj ファイル内で指定した既定のライブラリが検索されます。  
  
 [\/NODEFAULTLIB \(すべての既定のライブラリを無視\)](../../build/reference/nodefaultlib-ignore-libraries.md) オプションは、\/DEFAULTLIB:*library* の指定よりも優先されます。  [\/NODEFAULTLIB:library \(無視するライブラリ\)](../../build/reference/nodefaultlib-ignore-libraries.md) オプションと \/DEFAULTLIB:*library* オプションで同じライブラリを指定すると、前者の指定が優先されるためそのライブラリは検索されません。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
-   このリンカー オプションは、Visual Studio 開発環境では使用できません。  リンク フェーズにライブラリを追加するには、\[入力\] プロパティ ページの **\[追加の依存ファイル\]** プロパティを使用します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)