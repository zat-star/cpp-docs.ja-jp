---
title: "Platform::Collections::MapView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView クラス"
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Collections::MapView クラス
キーと値のペアのコレクションである、*マップ*への読み取り専用ビューを表します。  
  
## 構文  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = ::std::less<K>  
>  
ref class MapView sealed;  
```  
  
#### パラメーター  
 `K`  
 キー\/値ペア内のキーの型。  
  
 `V`  
 キー\/値ペア内の値の型。  
  
 `C`  
 並べ替えキーとして 2 つの要素値を比較して MapView 内の相対順序を決定できる関数オブジェクトを提供する型。 既定では、[::std::less\<K\>](../standard-library/less-struct.md) です。  
  
## 解説  
 MapView は、アプリケーション バイナリ インターフェイス \(ABI: Application Binary Interface\) を通じて渡される [Windows::Foundation::Collections::IMapView \<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409) インターフェイスの C\+\+ の具象実装です。 詳細については、「[Collections \(C\+\+\/CX\) \(コレクション \(C\+\+\/CX\)\)](../cppcx/collections-c-cx.md)」を参照してください。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[MapView::MapView コンストラクター](../cppcx/mapview-mapview-constructor.md)|MapView クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[MapView::First メソッド](../cppcx/mapview-first-method.md)|マップ ビュー内の最初の要素に初期化される反復子を返します。|  
|[MapView::HasKey メソッド](../cppcx/mapview-haskey-method.md)|現在の MapView に、指定されたキーが含まれているかどうかを判定します。|  
|[MapView::Lookup メソッド](../cppcx/mapview-lookup-method.md)|現在の MapView オブジェクト内の、指定されたキーの位置の要素を取得します。|  
|[MapView::Size メソッド](../cppcx/mapview-size-method.md)|現在の MapView オブジェクトの要素数を返します。|  
|[MapView::Split メソッド](../cppcx/mapview-split-method.md)|元の MapView オブジェクトを、2 つの MapView オブジェクトに分割します。|  
  
## 継承階層  
 `MapView`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) Platform 名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)