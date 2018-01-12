---
title: ".ファイルをリンカー入力として lib |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.AdditionalDependencies
dev_langs: C++
helpviewer_keywords:
- OMF libraries
- linking [C++], OMF libraries
- import libraries, linker files
- libraries [C++], .lib files as linker input
- COFF files, import libraries
- default libraries [C++], linker output
- default libraries [C++]
- defaults [C++], libraries
- .lib files
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 181c8c3e5e762f2f20d99ca2acadaf285e717b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lib-files-as-linker-input"></a>リンカー入力としての .lib ファイル
形式の標準ライブラリおよび COFF インポート ライブラリ、どちらも通常、拡張子であるリンクを受け入れます。 lib です。 標準ライブラリでは、オブジェクトが含まれており、LIB ツールによって作成されます。 インポート ライブラリは他のプログラムでのエクスポートに関する情報が含まれてし、作成するにはリンクによってエクスポートを含むプログラムをビルドするとき、または LIB ツールによってです。 標準的な作成またはインポート ライブラリに LIB の使用方法の詳細については、次を参照してください。 [LIB リファレンス](../../build/reference/lib-reference.md)です。 リンクを使用して、インポート ライブラリを作成する方法の詳細については、「、 [/DLL](../../build/reference/dll-build-a-dll.md)オプション。  
  
ライブラリは、ファイル名の引数、または既定のライブラリとしてリンクに指定されます。 リンクは、最初に、コマンドラインで指定されたライブラリを検索して外部参照を解決し、ライブラリがで指定された既定の[/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md)オプション、既定のライブラリが指定の .obj ファイル内とします。 パスを指定するには、ライブラリの名前、そのディレクトリでは、ライブラリのリンクが検索されます。 パスが指定されていないリンクからのリンクを実行して、ディレクトリにし、その後、LIB 環境変数で指定されたディレクトリで検索されます。  
  
## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>開発環境でリンカー入力としての .lib ファイルを追加するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**入力**プロパティ ページで、**リンカー**フォルダーです。  
  
3.  変更、**追加の依存関係**.lib ファイルを追加するプロパティです。  
  
## <a name="to-programmatically-add-lib-files-as-linker-input"></a>リンカー入力としての .lib ファイルをプログラムで追加するには  
  
-   参照してください[AdditionalDependencies](https://msdn.microsoft.com/library/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies.aspx)です。  
  
## <a name="example"></a>例  
次の例では、構築し、.lib ファイルを使用する方法を示します。 .Lib ファイルを最初に、ビルドするには。  
  
```cpp  
// lib_link_input_1.cpp  
// compile by using: cl /LD lib_link_input_1.cpp  
__declspec(dllexport) int Test() {  
   return 213;  
}  
```  
  
次に、作成した .lib ファイルを使用してこのサンプルをコンパイルします。  
  
```cpp  
// lib_link_input_2.cpp  
// compile by using: cl /EHsc lib_link_input_1.lib lib_link_input_2.cpp   
__declspec(dllimport) int Test();  
#include <iostream>  
int main() {  
   std::cout << Test() << std::endl;  
}  
```  
  
```Output  
213  
```  
  
## <a name="see-also"></a>参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)