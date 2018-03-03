---
title: "モジュール定義 (です。Def) ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49f5eb5b75bad22b59cb4fbb98554bbfd44d13b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="module-definition-def-files"></a>モジュール定義 (.def) ファイル
モジュール定義 (.def) ファイルは、エクスポート、属性、および他のプログラムについては、関連する問題に関する情報をリンカーを提供します。 .Def ファイルは、DLL を作成するときに最も役立ちます。 あるため[リンカー オプション](../../build/reference/linker-options.md)使用できるモジュール定義ステートメントではなく .def ファイルは通常必要ありません。 使用することも[方式](../../build/exporting-from-a-dll-using-declspec-dllexport.md)を指定する方法として関数をエクスポートします。  
  
 リンカーのフェーズ中に .def ファイルを呼び出すことができます、 [/DEF (モジュール定義ファイルの指定)](../../build/reference/def-specify-module-definition-file.md)リンカー オプション。  
  
 エクスポートを持たない .exe ファイルを作成している場合は、.def ファイルを使用すると、出力ファイルよりも大規模かつ低速の読み込みが作成されます。  
  
 例については、次を参照してください。 [DEF ファイルを使用する DLL からエクスポートする](../../build/exporting-from-a-dll-using-def-files.md)です。  
  
 詳細については、次のセクションを参照してください。  
  
-   [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [エクスポート](../../build/reference/exports.md)  
  
-   [ヒープサイズ](../../build/reference/heapsize.md)  
  
-   [ライブラリ](../../build/reference/library.md)  
  
-   [名](../../build/reference/name-c-cpp.md)  
  
-   [セクション](../../build/reference/sections-c-cpp.md)  
  
-   [スタックサイズ](../../build/reference/stacksize.md)  
  
-   [スタブ](../../build/reference/stub.md)  
  
-   [バージョン](../../build/reference/version-c-cpp.md)  
  
-   [予約語](../../build/reference/reserved-words.md)  
  
## <a name="see-also"></a>参照  
 [C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)   
 [リンカー オプション](../../build/reference/linker-options.md)  