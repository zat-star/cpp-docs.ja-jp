---
title: "入力ファイルのリンク |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d0cae9498d2c9b49e52cf56991d2425de39d7e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="link-input-files"></a>LINK の入力ファイル
リンカーは、オブジェクト、インポートおよび標準ライブラリ、リソース、モジュールの定義、およびコマンドの入力を含むファイルを提供します。 リンクは、ファイルの内容に関する想定を行うにはファイル拡張子を使用しません。 代わりに、リンクは、各入力ファイルがファイルの種類を判断するを調べます。  
  
 コマンドラインでのオブジェクト ファイルは、コマンドラインに表示される順序で処理されます。 ライブラリは、次に注意して同様に、コマンドラインの順序で検索されます: シンボルは未解決の場合、ライブラリからのオブジェクト ファイルで最初に検索されるのライブラリで、し、コマンドラインから次のライブラリ[/DEFAULTLIB (既定のライブラリの指定)](../../build/reference/defaultlib-specify-default-library.md)ディレクティブは、その後に、コマンドラインの先頭のすべてのライブラリです。  
  
> [!NOTE]
>  リンクでは、応答ファイルおよび順序ファイルでコメントの始まりとしてセミコロン (またはその他の文字) を不要になった受け取ります。 セミコロンは、モジュール定義ファイル (.def) 内のコメントの始まりとしてのみ認識されます。  
  
 リンクは、入力ファイルの次の種類を使用します。  
  
-   [.obj ファイル](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [.netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [.lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [.exp ファイル](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [.def ファイル](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [.pdb ファイル](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [.res ファイル](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [.exe ファイル](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [.txt ファイル](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [.ilk ファイル](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)