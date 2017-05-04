---
title: "Platform::Collections::UnorderedMap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap"
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Collections::UnorderedMap クラス
キー\/値ペアのコレクションである順序なしの*マップ*を表します。  
  
## 構文  
  
```scr  
template <  
   typename K,  
   typename V,  
   typename C = std::equal_to<K>  
>  
ref class Map sealed;  
```  
  
#### パラメーター  
 `K`  
 キー\/値ペア内のキーの型。  
  
 `V`  
 キー\/値ペア内の値の型。  
  
 `C`  
 並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 既定では、[std::equal\_to\<K\>](../standard-library/equal-to-struct.md) です。  
  
## 解説  
 使用できる型は次のとおりです。  
  
-   整数  
  
-   インターフェイス クラス ^  
  
-   パブリック ref クラス ^  
  
-   value struct  
  
-   パブリック列挙型クラス  
  
 UnorderedMap は、基本的に [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型のストレージをサポートする [std::unordered\_map](../standard-library/unordered-map-class.md) のラッパーです。 パブリック [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] インターフェイスを通じて渡される [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408) 型と [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) 型の具象実装です。 パブリックの戻り値またはパラメーターで Platform::Collections::UnorderedMap 型を使用しようとすると、コンパイル エラー C3986 が発生します。 エラーを修正するには、パラメーターや戻り値の型を [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408) に変更します。  
  
 詳細については、「[コレクション](../cppcx/collections-c-cx.md)」を参照してください。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|UnorderedMap::UnorderedMap コンストラクター|マップ クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[UnorderedMap::Clear メソッド](../cppcx/unorderedmap-clear-method.md)|現在のマップ オブジェクトから、すべてのキー\/値ペアを削除します。|  
|[UnorderedMap::First メソッド](../cppcx/unorderedmap-first-method.md)|マップ内の最初の要素を指定する反復子を返します。|  
|[UnorderedMap::GetView メソッド](../cppcx/unorderedmap-getview-method.md)|現在のマップの読み取り専用ビューである Platform::Collections::UnorderedMapView クラスを返します。|  
|[UnorderedMap::HasKey メソッド](../cppcx/unorderedmap-haskey-method.md)|指定したキーが現在のマップに格納されているかどうかを判定します。|  
|[UnorderedMap::Insert メソッド](../cppcx/unorderedmap-insert-method.md)|指定したキー\/値ペアを現在のマップ オブジェクトに追加します。|  
|[UnorderedMap::Lookup メソッド](../cppcx/unorderedmap-lookup-method.md)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|  
|[UnorderedMap::Remove メソッド](../cppcx/unorderedmap-remove-method.md)|指定したキー\/値ペアを現在のマップ オブジェクトから削除します。|  
|[UnorderedMap::Size メソッド](../cppcx/unorderedmap-size-method.md)|現在のマップ オブジェクト内の要素数を返します。|  
  
### イベント  
  
|||  
|-|-|  
|名前|説明|  
|[Map::MapChanged イベント](../cppcx/map-mapchanged-event.md) `event`|マップが変更されたときに発生します。|  
  
## 継承階層  
 `UnorderedMap`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) Platform 名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md)   
 [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)   
 [コレクション](../cppcx/collections-c-cx.md)   
 [C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)