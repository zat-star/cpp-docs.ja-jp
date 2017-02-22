---
title: "/ALIGN (セクションの配置) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Alignment"
  - "/align"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALIGN リンカー オプション"
  - "ALIGN リンカー オプション"
  - "-ALIGN リンカー オプション"
  - "セクション配置"
  - "sections"
  - "sections, 指定 (アライメントを)"
ms.assetid: f2f8ac24-e90e-4bea-8205-f2960a3b1740
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /ALIGN (セクションの配置)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALIGN[:number]  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 `number`  
 配置の値。  
  
## 解説  
 \/ALIGN オプションは、プログラムのリニア アドレス空間内の各セクションの配置を指定します。  引数 `number` ではバイト数を 2 の累乗で指定します。  既定値は 4 KB \(4096\) です。  配置によって無効なイメージが生成される場合は、警告が出力されます。  
  
 デバイス ドライバーなどのアプリケーションを作成する場合以外は、配置を変更する必要はありません。  
  
 [\/SECTION](../../build/reference/section-specify-section-attributes.md) オプションに align パラメーターを指定して特定のセクションの配置を変更できます。  
  
 配置の値に、一番大きいセクション配置より小さい値を指定することはできません。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)