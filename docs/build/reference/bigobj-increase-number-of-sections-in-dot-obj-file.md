---
title: "/bigobj (.obj ファイル内のセクションの数を増やす) | Microsoft Docs"
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
  - "/bigobj"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/bigobj コンパイラ オプション [C++]"
  - "bigobj コンパイラ オプション [C++]"
  - "-bigobj コンパイラ オプション [C++]"
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /bigobj (.obj ファイル内のセクションの数を増やす)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/bigobj** は、オブジェクト ファイルに格納できるセクションの数を増やします。  
  
## 構文  
  
```  
/bigobj  
```  
  
## 解説  
 既定では、オブジェクト ファイルはアドレス指定可能なセクションを最大 65,536 \(2^16\) 保持できます。  これは、どのターゲット プラットフォームを指定したかにかかわらない場合です。  **\/bigobj** は、このアドレスの量を 4,294,967,296 \(2^32\) に増やします。  
  
 ほとんどのモジュールでは、65,536 を超えるセクションを格納する .obj ファイルを生成することはありません。  しかし、マシンによって生成されるコード、またはテンプレート ライブラリを多用するコードでは、より多くのセクションを保持できる .obj ファイルを必要とする可能性があります。  **\/bigobj** は、Windows ストア プロジェクトで既定で有効になっています。コンピューターが生成した XAML コードに多数のヘッダーが含まれているためです。  Windows ストア アプリのプロジェクトでこのオプションを無効にすると、コンパイラ エラー C1128 が発生する可能性が高くなります。  
  
 Visual C\+\+ 2005 より前のバージョンに付属していたリンカーは、**\/bigobj** を指定して作成された .obj ファイルを読み取ることができません。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)