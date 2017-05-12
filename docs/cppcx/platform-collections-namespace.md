---
title: "Platform::Collections 名前空間 | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Collections 名前空間"
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Collections 名前空間
Platform::Collection 名前空間には `Map`、`MapView`、`Vector`、および `VectorView` の各クラスが含まれています。 これらのクラスは、[Windows::Foundation::Collections](http://go.microsoft.com/fwlink/p/?LinkId=262645) 名前空間に定義されている、対応するインターフェイスの具象実装です。 具体的なコレクション型は、\(Javascript または C\# で書かれたプログラムが C \+\+ コンポーネントを呼び出すなど\) ABI を越えて移植することはできませんが、対応するインターフェイスの型に暗黙的に変換できます。 たとえば、コレクションを設定して返すパブリック メソッドを実装する場合は、[Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) を使用して内部的にコレクションを実装し、[Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) を戻り値の型として使用します。 詳細については、次のトピックを参照してください。[コレクション](../cppcx/collections-c-cx.md) および[C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
 Platform::Collections::Vector は [std::vector](../Topic/vector%20Class%201.md) から構築でき、[Platform::Collections::Map](../cppcx/platform-collections-map-class.md) は [std::map](../standard-library/map-class.md) から構築できます。  
  
 また、Platform::Collection 名前空間は、末尾挿入反復子および入力反復子、および `Vector` と `VectorView` の各反復子のサポートを提供します。  
  
 Platform::Collection 名前空間で型を使用するには、collection.h ヘッダーを含める \(`#include`\) 必要があります。  
  
## 構文  
  
```cpp  
  
#include <collection.h>  
using namespace Platform::Collection;  
```  
  
## メンバー  
 この名前空間には、次のメンバーが含まれます。  
  
|名前|説明|  
|--------|--------|  
|[Platform::Collections::BackInsertIterator クラス](../cppcx/platform-collections-backinsertiterator-class.md)|コレクションの末尾に要素を挿入する反復子を表します。|  
|[Platform::Collections::InputIterator クラス](../cppcx/platform-collections-inputiterator-class.md)|コレクションの先頭に要素を挿入する反復子を表します。|  
|[Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)|キーによりアクセスされるキーと値のペアの変更可能なコレクションを表します。[std::map](../standard-library/map-class.md) に似ています。|  
|[Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)|キーによりアクセスされるキーと値のペアの読み取り専用のコレクションを表します。|  
|[Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)|要素の変更可能なシーケンスを表します。[std::vector](../Topic/vector%20Class%201.md) に似ています。|  
|[Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)|`Vector` コレクションを走査する反復子を表します。|  
|[Platform::Collections::VectorView クラス](../cppcx/platform-collections-vectorview-class.md)|要素の読み取り専用のシーケンスを表します。|  
|[Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)|`VectorView` コレクションを走査する反復子を表します。|  
  
## 継承階層  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)  
  
## 必要条件  
 **メタデータ:** platform.winmd  
  
 **名前空間:** Platform::Collections  
  
 **コンパイラ オプション:** \/ZW  
  
## 参照  
 [\(NOTINBUILD\) プラットフォーム名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)