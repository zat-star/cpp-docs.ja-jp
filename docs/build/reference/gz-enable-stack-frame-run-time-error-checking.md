---
title: "/GZ (スタック フレームのランタイム エラー チェックの有効化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gz"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GZ コンパイラ オプション [C++]"
  - "デバッグ ビルド, キャッチ (リリース ビルドのエラーを)"
  - "GZ コンパイラ オプション [C++]"
  - "-GZ コンパイラ オプション [C++]"
  - "リリース ビルド エラー"
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /GZ (スタック フレームのランタイム エラー チェックの有効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/RTC \(ランタイム エラー チェック\)](../../build/reference/rtc-run-time-error-checks.md) オプションと同じ操作を実行します。  使用は推奨されていません。  
  
## 構文  
  
```  
/GZ  
```  
  
## 解説  
 **\/GZ** は、最適化されていない \([\/Od \(無効 \(デバッグ\)\)](../../build/reference/od-disable-debug.md)\) ビルドだけで使用されます。  
  
 **\/GZ** は使用されなくなりました。代わりに、[\/RTC \(ランタイム エラー チェック\)](../../build/reference/rtc-run-time-error-checks.md) を使用してください。  詳細については、「[Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ja-jp/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  \[追加のオプション\]ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)