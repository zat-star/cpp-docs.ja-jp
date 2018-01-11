---
title: "コンパイラの警告 (レベル 1) C4727 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4727
dev_langs: C++
helpviewer_keywords: C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 813c2ab18cc81c4477ae094e6c2aa771e3135b7a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4727"></a>コンパイラの警告 (レベル 1) C4727
"PCH の obj_file_1 および obj_file_2 で検出された同じタイムスタンプを持つ pch_file という名前です。  最初の PCH を使用します。  
  
 C4727 発生で複数のコンパイル単位をコンパイルするときに**/Yc**コンパイラが同じ .pch タイムスタンプを持つすべての .obj ファイルをマークすることであるとします。  
  
 を解決する 1 つのソース ファイルをコンパイル**/Yc/c** (pch を作成する)、し、他のユーザーとは別に**/Yu/c** (pch を使用)、それらをリンクします。  
  
 そのため、以下し、C4727 を生成する場合:  
  
 **cl/clr/GL a.cpp b.cpp c.cpp/Ycstdafx.h**  
  
 次の代わりに実行します。  
  
 **cl/clr/GL a.cpp/Ycstdafx.h/c**  
  
 **cl/clr/GL b.cpp c.cpp/Yustdafx.h/link a.obj**  
  
 詳細については、次のトピックを参照してください。  
  
-   [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)