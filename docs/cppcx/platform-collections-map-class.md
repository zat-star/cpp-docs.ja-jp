---
title: "Platform::Collections::Map クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map クラス (C++/Cx)"
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: 19
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 19
---
# Platform::Collections::Map クラス
キー\/値ペアのコレクションである*マップ*を表します。  
  
## 構文  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>  
ref class Map sealed;  
```  
  
#### パラメーター  
 `K`  
 キー\/値ペア内のキーの型。  
  
 `V`  
 キー\/値ペア内の値の型。  
  
 `C`  
 並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 既定では、[std::less\<K\>](../standard-library/less-struct.md) です。  
  
 \_\_is\_valid\_winrt\_type\(\)  
 K および V の型を検証し、型がマップ内に格納できない場合は簡易エラー メッセージを示す、コンパイラにより生成される関数。  
  
## 解説  
 使用できる型は次のとおりです。  
  
-   整数  
  
-   インターフェイス クラス ^  
  
-   パブリック ref クラス ^  
  
-   value struct  
  
-   パブリック列挙型クラス  
  
 マップは、基本的に [std::map](../standard-library/map-class.md) のラッパーです。 パブリック [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] インターフェイスを通じて渡される [Windows::Foundation::Collections::IMap\<Windows::Foundation::Collections::IKeyValuePair\<K,V\>\>](http://go.microsoft.com/fwlink/p/?LinkId=262408) 型と [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) 型の具象実装です。 パブリックの戻り値またはパラメーターで `Platform::Collections::Map` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 このエラーを修正するには、パラメーターまたは戻り値の型を [Windows::Foundation::Collections::IMap\<K,V](http://go.microsoft.com/fwlink/p/?LinkId=262408) に変更します。  
  
 詳細については、「[コレクション](../cppcx/collections-c-cx.md)」を参照してください。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Map::Map コンストラクター](../cppcx/map-map-constructor.md)|マップ クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[Map::Clear メソッド](../cppcx/map-clear-method.md)|現在のマップ オブジェクトから、すべてのキー\/値ペアを削除します。|  
|[Map::First メソッド](../cppcx/map-first-method.md)|マップ内の最初の要素を指定する反復子を返します。|  
|[Map::GetView メソッド](../cppcx/map-getview-method.md)|現在のマップの読み取り専用ビュー \([Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)\) を返します。|  
|[Map::HasKey メソッド](../cppcx/map-haskey-method.md)|指定したキーが現在のマップに格納されているかどうかを判定します。|  
|[Map::Insert メソッド](../cppcx/map-insert-method.md)|指定したキー\/値ペアを現在のマップ オブジェクトに追加します。|  
|[Map::Lookup メソッド](../cppcx/map-lookup-method.md)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|  
|[Map::Remove メソッド](../cppcx/map-remove-method.md)|指定したキー\/値ペアを現在のマップ オブジェクトから削除します。|  
|[Map::Size メソッド](../cppcx/map-size-method.md)|現在のマップ オブジェクト内の要素数を返します。|  
  
### イベント  
  
|||  
|-|-|  
|名前|説明|  
|[Map::MapChanged イベント](../cppcx/map-mapchanged-event.md) `event`|マップが変更されたときに発生します。|  
  
## 継承階層  
 `Map`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) Platform 名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)