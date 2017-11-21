---
title: "Platform::collections Namespace |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/25/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Platform::Collections
dev_langs: C++
helpviewer_keywords: Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 04514a4d4ddbba8b6c28e35e964deb153803580f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollections-namespace"></a>Platform::Collections 名前空間
Platform::Collection 名前空間には `Map`、 `MapView`、 `Vector`、および `VectorView` の各クラスが含まれています。 これらのクラスは、 [Windows::Foundation::Collections](http://go.microsoft.com/fwlink/p/?LinkId=262645) 名前空間に定義されている、対応するインターフェイスの具象実装です。 具体的なコレクション型は、(Javascript または C# で書かれたプログラムが C ++ コンポーネントを呼び出すなど) ABI を越えて移植することはできませんが、対応するインターフェイスの型に暗黙的に変換できます。 たとえば、コレクションを設定して返すパブリック メソッドを実装する場合は、 [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) を使用して内部的にコレクションを実装し、 [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) を戻り値の型として使用します。 詳細については、次を参照してください。[コレクション](../cppcx/collections-c-cx.md)と[C++ での Windows ランタイム コンポーネントの作成](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)です。  
  
 Platform::Collections::Vector は [std::vector](../standard-library/vector-class.md) から構築でき、 [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) は [std::map](../standard-library/map-class.md)から構築できます。  
  
 また、platform::collection 名前空間は挿入反復子および入力反復子のサポートを提供および`Vector`と`VectorView`反復子。  
  
 Platform::Collection 名前空間で型を使用するには、collection.h ヘッダーを含める (`#include`) 必要があります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
  
#include <collection.h>  
using namespace Platform::Collection;  
```  
  
### <a name="members"></a>メンバー  
 この名前空間には、次のメンバーが含まれます。  
  
|名前|説明|  
|----------|-----------------|  
|[Platform::Collections::BackInsertIterator クラス](../cppcx/platform-collections-backinsertiterator-class.md)|コレクションの末尾に要素を挿入する反復子を表します。|  
|[Platform::Collections::InputIterator クラス](../cppcx/platform-collections-inputiterator-class.md)|コレクションの先頭に要素を挿入する反復子を表します。|  
|[Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)|キーによりアクセスされるキーと値のペアの変更可能なコレクションを表します。 [std::map](../standard-library/map-class.md)に似ています。|  
|[Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)|キーによりアクセスされるキーと値のペアの読み取り専用のコレクションを表します。|  
|[Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)|要素の変更可能なシーケンスを表します。 [std::vector](../standard-library/vector-class.md)に似ています。|  
|[Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)|`Vector` コレクションを走査する反復子を表します。|  
|[Platform::Collections::VectorView クラス](../cppcx/platform-collections-vectorview-class.md)|要素の読み取り専用のシーケンスを表します。|  
|[Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)|`VectorView` コレクションを走査する反復子を表します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)  
  
### <a name="requirements"></a>要件  
 **メタデータ:** platform.winmd  
  
 **名前空間:** Platform::Collections  
  
 **コンパイラ オプション:** /ZW  
  
## <a name="see-also"></a>関連項目  
 [プラットフォーム Namespace](../cppcx/platform-namespace-c-cx.md)