---
title: "/PROFILE (パフォーマンス ツール プロファイラー) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.Profile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PROFILE リンカー オプション"
  - "-PROFILE リンカー オプション"
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PROFILE (パフォーマンス ツール プロファイラー)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。  
  
## 構文  
  
```  
/PROFILE  
```  
  
## 解説  
 \/PROFILE は、以下のリンカー オプションを暗黙に指定します。  
  
-   [\/OPT:REF](../../build/reference/opt-optimizations.md)  
  
-   \/OPT:NOICF  
  
-   [\/INCREMENTAL:NO](../../build/reference/incremental-link-incrementally.md)  
  
-   [\/FIXED:NO](../../build/reference/fixed-fixed-base-address.md)  
  
 \/PROFILE を指定すると、リンカーがプログラム イメージに再配置セクションを生成します。再配置セクションでは、プロファイラーがプログラム イメージを変換してプロファイル データを取得できます。  
  
 **\/PROFILE** は Enterprise \(チーム開発\) バージョンでのみ利用できます。PREfast の詳細については、「[C\/C\+\+ のコード分析の概要](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[詳細\]** プロパティ ページをクリックします。  
  
5.  **\[プロファイル\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)