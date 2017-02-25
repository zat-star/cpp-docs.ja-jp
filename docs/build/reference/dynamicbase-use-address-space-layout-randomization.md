---
title: "/DYNAMICBASE (ASLR (Address Space Layout Randomization) の使用) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RandomizedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE リンカー オプション"
  - "DYNAMICBASE リンカー オプション"
  - "-DYNAMICBASE リンカー オプション"
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /DYNAMICBASE (ASLR (Address Space Layout Randomization) の使用)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[windowsver](../Token/windowsver_md.md)] の ASLR \(Address Space Layout Randomization\) 機能を使用してロード時にランダムに再ベースできる実行可能イメージを生成するかどうかを指定します。  
  
## 構文  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## 解説  
 既定では、\/DYNAMICBASE が有効になっています。  
  
 このオプションは、ロード時にアプリケーションをランダムに再ベースするかどうかを示すように実行可能ファイルのヘッダーを変更します。  
  
 ASLR 機能は [!INCLUDE[windowsver](../Token/windowsver_md.md)] でサポートされています。  
  
### このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[詳細\]** プロパティ ページをクリックします。  
  
5.  **\[ランダム化されたベース アドレス\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)