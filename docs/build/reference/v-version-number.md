---
title: "/V (バージョン番号) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/v"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/V コンパイラ オプション [C++]"
  - "埋め込む (バージョン文字列を)"
  - "V コンパイラ オプション [C++]"
  - "-V コンパイラ オプション [C++]"
  - "バージョン番号, 指定 (.obj の)"
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /V (バージョン番号)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列を .obj ファイルに埋め込みます。  使用は推奨されていません。  
  
## 構文  
  
```  
/Vstring  
```  
  
## Arguments  
 `string`  
 .obj ファイルに埋め込まれるバージョン番号または著作権表記を指定する文字列。  
  
## 解説  
 .obj ファイルに埋め込む文字列としては、バージョン番号や著作権表記があります。  空白やタブが文字列に含まれている場合は、それらを二重引用符 \("\) で囲む必要があります。  二重引用符が文字列に含まれている場合は、その直前に円記号 \(\\\) を付ける必要があります。  **\/V** と `string` の間にはスペースを挿入してもかまいません。  
  
 [コメント](../../preprocessor/comment-c-cpp.md) にコメント型引数 compiler を指定すると、コンパイラの名前とバージョン番号を .obj ファイルに埋め込むことができます。  
  
 **\/V** は使用しないでください。**\/V** は主に仮想デバイス ドライバー \(VxD\) の構築をサポートするために使用されていましたが、[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] ツールセットでは VxD の構築はサポートされなくなりました。  詳細については、「[Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ja-jp/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)」を参照してください。  
  
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