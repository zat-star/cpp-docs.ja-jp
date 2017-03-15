---
title: "/Fe (EXE ファイルの名前の指定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/fe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fe コンパイラ オプション [C++]"
  - "実行可能ファイル, 名前を変更"
  - "Fe コンパイラ オプション [C++]"
  - "-Fe コンパイラ オプション [C++]"
  - "名前の変更 (ファイルの) コンパイラ オプション [C++]"
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Fe (EXE ファイルの名前の指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラによって生成される .exe ファイルと DLL のファイル名とディレクトリを指定します。  
  
## 構文  
  
```  
/Fepathname  
```  
  
## 解説  
 このオプションを指定しない場合は、コマンド ラインで最初に指定したソース ファイルまたはオブジェクト ファイルの基本名に拡張子 .exe または .dll が付加された名前が既定のファイル名として指定されます。  
  
 リンクを行わずにコンパイルする [\/c \(リンクを行わないコンパイル\)](../../build/reference/c-compile-without-linking.md) を指定すると、**\/Fe** は無効になります。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーをクリックします。  
  
3.  **\[全般\]** プロパティ ページをクリックします。  
  
4.  **\[出力ファイル\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>」を参照してください。  
  
## 使用例  
 次のコマンド ラインは、現在のディレクトリにあるすべての C ソース ファイルをコンパイルおよびリンクします。  この結果、PROCESS.exe という名前の実行可能ファイルが C:\\BIN ディレクトリに生成されます。  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## 使用例  
 次のコマンド ラインでは、最初のソース ファイルまたはオブジェクト ファイルの基本名と同じ名前の実行可能ファイルが `C:\BIN` に生成されます。  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## 参照  
 [出力ファイル \(\/F\) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [パス名の指定](../Topic/Specifying%20the%20Pathname.md)