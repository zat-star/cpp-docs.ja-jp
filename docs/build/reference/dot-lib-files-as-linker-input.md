---
title: "リンカー入力としての .lib ファイル | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.AdditionalDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".lib ファイル"
  - "COFF ファイル, インポート ライブラリ"
  - "既定のライブラリ [C++]"
  - "既定のライブラリ [C++], リンカー出力"
  - "既定 [C++], ライブラリ"
  - "インポート ライブラリ, リンカー ファイル"
  - "ライブラリ [C++], .lib ファイル (リンカー入力)"
  - "リンク [C++], OMF ライブラリ"
  - "OMF ライブラリ"
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー入力としての .lib ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK では、COFF 形式の標準ライブラリもインポート ライブラリもリンクできます。通常、この 2 つのライブラリの拡張子は、どちらも .lib になります。  標準ライブラリは、オブジェクトから構成され、LIB ツールで作成されたライブラリです。  インポート ライブラリは、ほかのプログラムのエクスポート シンボルに関する情報が入っているライブラリです。このライブラリは、シンボルをエクスポートするプログラムのビルド時に LINK によって作成されるか、LIB ツールによって作成されます。  LIB ツールを使って標準ライブラリやインポート ライブラリを作成する方法については、「[LIB リファレンス](../../build/reference/lib-reference.md)」を参照してください。  LINK を使ってインポート ライブラリを作成する方法については、「[\/DLL \(DLL のビルド\)](../../build/reference/dll-build-a-dll.md)」を参照してください。  
  
 入力ライブラリとしては、コマンド ラインで名前が指定されたライブラリと既定のライブラリがあります。  LINK は外部参照を解決するときに、まずコマンド ラインで指定されたライブラリを検索し、次に [\/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md) オプションで指定された既定のライブラリを検索します。その後、.obj ファイルで指定された既定のライブラリを検索します。  ライブラリ名と共にパスが指定されている場合は、指定したディレクトリでライブラリを検索します。  パスが指定されていない場合は、まず LINK が起動したディレクトリを検索し、次に環境変数 LIB で指定されたディレクトリを検索します。  
  
### 開発環境で .lib ファイルをリンカー入力として追加するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[入力\] プロパティ ページをクリックします。  
  
4.  **\[追加の依存ファイル\]** プロパティを変更します。  
  
### プログラムによって .lib ファイルをリンカー入力として追加するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalDependencies%2A>」を参照してください。  
  
## 使用例  
 .lib ファイルのビルド方法および使用方法を次の例に示します。  
  
```  
// lib_link_input_1.cpp  
// compile with: /LD  
__declspec(dllexport) int Test() {  
   return 213;  
}  
```  
  
## 使用例  
 その後、次を実行します。  
  
```  
// lib_link_input_2.cpp  
// compile with: /EHsc lib_link_input_1.lib  
__declspec(dllimport) int Test();  
#include <iostream>  
int main() {  
   std::cout << Test() << std::endl;  
}  
```  
  
  **213**   
## 参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)