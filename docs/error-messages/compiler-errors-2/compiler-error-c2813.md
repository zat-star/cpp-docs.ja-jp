---
title: "コンパイラ エラー C2813 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fc5f5437751abf6bcb11299e8484a199275db970
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2813"></a>コンパイラ エラー C2813
\#インポートは/MP でサポートされていません  
  
 C2813 は、コンパイラのコマンドで指定する場合に出力されますが、 **/MP**コンパイラ オプションと次の 2 つ以上のファイルをコンパイル、および 1 つまたは複数のファイルが含まれています、[#import](../../preprocessor/hash-import-directive-cpp.md)プリプロセッサ ディレクティブです。 [#Import](../../preprocessor/hash-import-directive-cpp.md)ディレクティブが指定されたタイプ ライブラリ内の型から C++ クラスを生成し、し、それらのクラスを次の 2 つのヘッダー ファイルに書き込みます。 [#Import](../../preprocessor/hash-import-directive-cpp.md)ディレクティブはそれらの単位と同時に同じヘッダー ファイルを作成しようとすると競合する複数のコンパイル単位では、同じタイプ ライブラリをインポートする場合にサポートされていません。  
  
 このコンパイラ エラーが発生し、 **/MP**コンパイラ オプションが追加されて[!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)]です。  
  
## <a name="example"></a>例  
 次の例では C2813 が生成されます。 "compile with:" コメントのコマンド ラインは、 **/MP** および **/c** コンパイラ オプションを使用して複数のファイルをコンパイルすることをコンパイラに示します。 少なくとも 1 つのファイルが含まれています、 [#import](../../preprocessor/hash-import-directive-cpp.md)ディレクティブです。 この例のテストのために、同じファイルを 2 回使用します。  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```
