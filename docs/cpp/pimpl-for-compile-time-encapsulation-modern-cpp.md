---
title: "コンパイル時のカプセル化 (Modern C) Pimpl |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a109015f3d30b04eaf89e769e1265c49663599f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>コンパイル時のカプセル化の Pimpl (Modern C++)
*Pimpl 表現*インターフェイスを分離したり結合度を最小限に抑えるの実装を非表示に最新の C++ 手法です。 Pimpl はの短縮形「へのポインターの実装です」 既に概念を理解するが、Cheshire Cat またはコンパイラのファイアウォールの表現形式のようなその他の名前を知っている可能性があります。  
  
## <a name="why-use-pimpl"></a>Pimpl を使用する理由  
 Pimpl 表現形式が、ソフトウェア開発ライフ サイクルを改善する方法を次に示します。  
  
-   コンパイルの依存関係の最小化します。  
  
-   インターフェイスと実装の分離。  
  
-   移植性。  
  
## <a name="pimpl-header"></a>Pimpl ヘッダー  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 および当てオブジェクトのレイアウトを再構築を連鎖 pimpl 表現形式を回避できます。 (推移的に) 一般的な種類にも適しています。  
  
## <a name="pimpl-implementation"></a>Pimpl 実装  
 定義、 `impl` .cpp ファイル内のクラスです。  
  
```cpp  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 例外をスローしないスワップ特殊化のサポートを追加するかどうかを検討してください。  
  
## <a name="see-also"></a>参照  
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)