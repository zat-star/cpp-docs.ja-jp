---
title: "コンパイラの警告 (レベル 1) C4727 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4727
dev_langs:
- C++
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c3d77b053fb866a16e6642ba2e6a24ff6d85798f
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4727"></a>コンパイラの警告 (レベル 1) C4727
"PCH の obj_file_1 や obj_file_2 に含まれる同じタイムスタンプを持つ pch_file という名前です。  最初の PCH を使用しています。  
  
 複数のコンパイル単位をコンパイルするときに発生する C4727 **/Yc**コンパイラが同じ .pch タイムスタンプを持つすべての .obj ファイルをマークすることであるとします。  
  
 を解決するのに&1; つのソース ファイルをコンパイル**/Yc/c** (pch を作成します) を使用して個別にコンパイル、他のユーザーと**/Yu/c** (pch を使用します)、それらをリンクします。  
  
 そのため、以下し、C4727 を生成する場合:  
  
 **cl/clr/GL a.cpp b.cpp c.cpp/Ycstdafx.h**  
  
 次の代わりに実行します。  
  
 **cl/clr/GL a.cpp/Ycstdafx.h/c**  
  
 **cl/clr/GL b.cpp c.cpp/Yustdafx.h/link a.obj**  
  
 詳細については、次のトピックを参照してください。  
  
-   [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)
