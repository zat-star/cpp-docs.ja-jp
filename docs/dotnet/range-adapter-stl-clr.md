---
title: "range_adapter (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::range_adapter
dev_langs: C++
helpviewer_keywords: range_adapter class [STL/CLR]
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b9adb22c14fb5b59dfb4e89e69c724ca8c7462bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rangeadapter-stlclr"></a>range_adapter (STL/CLR)
いくつかの基本クラス ライブラリ (BCL) インターフェイスを実装するために使用する反復子のペアをラップするテンプレート クラス。 使用する、range_adapter 操作 STL/CLR 範囲 BCL コレクションの場合と同様です。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>パラメーター  
 iter  
 ラップされた反復子に関連付けられている型。  
  
## <a name="members"></a>メンバー  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[range_adapter::range_adapter (STL/CLR)](../dotnet/range-adapter-range-adapter-stl-clr.md)|アダプター オブジェクトを構築します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[range_adapter::operator= (STL/CLR)](../dotnet/range-adapter-operator-assign-stl-clr.md)|格納された反復子のペアを置き換えます。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|コレクション内の要素を反復処理します。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|コレクション内の型指定された要素を反復処理.|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを保持します。|  
  
## <a name="remarks"></a>コメント  
 Range_adapter は、さらに要素のシーケンスを区切る反復子のペアを格納します。 オブジェクトは、順序内の要素を反復処理するのに便利な次の 4 つの BCL インターフェイスを実装します。 BCL コンテナーと同様に STL/CLR 範囲を操作するのにには、このテンプレート クラスを使用します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アダプター/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)