---
title: "コンパイラ エラー C2989 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2989
dev_langs:
- C++
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a6fb6c0a2b2c3a7608c10794e77ecc8b5573dc7b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2989"></a>コンパイラ エラー C2989
'class': クラス型は既に非クラス型として宣言されて  
  
 ジェネリック クラスまたはテンプレートには、非テンプレートまたは非ジェネリック クラスが再定義します。 ヘッダー ファイルの競合を確認します。  
  
 クラス テンプレートの部分的特殊化を使用している場合は、サポート技術情報記事 Q240866 を参照してください。  
  
 次の例では、C2989 が生成されます。  
  
```  
// C2989.cpp  
// compile with: /c  
class C{};  
  
template <class T>  
class C{};  // C2989  
class C2{};  
```  
  
 C2989 は、ジェネリックを使用するときにも発生します。  
  
```  
// C2989b.cpp  
// compile with: /clr /c  
ref class GC1;  
  
generic <typename T> ref class GC1;   // C2989  
template <typename T> ref class GC2;  
  
generic <typename T> ref class GC2;   // C2989  
generic <typename T> ref class GCb;  
template <typename T> ref class GC2;  
generic <typename T> ref class GCc;  
```
