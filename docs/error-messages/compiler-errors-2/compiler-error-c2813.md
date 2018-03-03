---
title: "コンパイラ エラー C2813 |Microsoft ドキュメント"
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
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cc6ac0e287894dc2202814c55dac37569650f5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2813"></a>コンパイラ エラー C2813
\#インポートは/MP でサポートされていません  
  
 C2813 は、コンパイラのコマンドで **/MP** コンパイラ オプションとコンパイルする 2 つ以上のファイルを指定し、1 つ以上のファイルに[#import](../../preprocessor/hash-import-directive-cpp.md) プリプロセッサ ディレクティブが含まれている場合に生成されます。 [#Import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブによって、指定したタイプ ライブラリ内の型から C++ クラスが生成され、これらのクラスが 2 つのヘッダー ファイルに書き込まれます。 複数のコンパイル単位で同じタイプ ライブラリがインポートされる場合、それらの単位は同時に同じヘッダー ファイルに書き込もうとすると競合するため、 [#Import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブはサポートされていません。  
  
 このコンパイラ エラーが発生し、 **/MP**コンパイラ オプションは Visual Studio 2008 の新機能です。  
  
## <a name="example"></a>例  
 次の例では C2813 が生成されます。 "compile with:" コメントのコマンド ラインは、 **/MP** および **/c** コンパイラ オプションを使用して複数のファイルをコンパイルすることをコンパイラに示します。 少なくとも 1 つのファイルに [#import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブが含まれています。 この例のテストのために、同じファイルを 2 回使用します。  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```