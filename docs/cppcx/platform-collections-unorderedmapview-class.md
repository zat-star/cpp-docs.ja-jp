---
title: "Platform::Collections::UnorderedMapView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView"
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Collections::UnorderedMapView クラス
キーと値のペアのコレクションである、*マップ*への読み取り専用ビューを表します。  
  
## 構文  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>  
>  
ref class UnorderedMapView sealed;  
```  
  
#### パラメーター  
 `K`  
 キー\/値ペア内のキーの型。  
  
 `V`  
 キー\/値ペア内の値の型。  
  
 `C`  
 2 つのキー値を比較して等価性を確認できる関数オブジェクトを提供する型。 既定では、[std::equal\_to\<K\>](../standard-library/equal-to-struct.md) です。  
  
## 解説  
 UnorderedMapView は、アプリケーション バイナリ インターフェイス \(ABI: Application Binary Interface\) を通じて渡される [Windows::Foundation::Collections::IMapView\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409) インターフェイスの C\+\+ の具象実装です。 詳細については、「[Collections \(C\+\+\/CX\) \(コレクション \(C\+\+\/CX\)\)](../cppcx/collections-c-cx.md)」を参照してください。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[UnorderedMapView::UnorderedMapView コンストラクター](../cppcx/unorderedmapview-unorderedmapview-constructor.md)|UnorderedMapView クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[UnorderedMapView::First メソッド](../cppcx/unorderedmapview-first-method.md)|マップ ビュー内の最初の要素に初期化される反復子を返します。|  
|[UnorderedMapView::HasKey メソッド](../cppcx/unorderedmapview-haskey-method.md)|指定したキーが現在の UnorderedMapView に格納されているかどうかを判定します。|  
|[UnorderedMapView::Lookup メソッド](../cppcx/unorderedmapview-lookup-method.md)|現在の UnorderedMapView オブジェクト内の指定されたキーの位置の要素を取得します。|  
|[UnorderedMapView::Size メソッド](../cppcx/unorderedmapview-size-method.md)|現在の UnorderedMapView オブジェクトの要素数を返します。|  
|[UnorderedMapView::Split メソッド](../cppcx/unorderedmapview-split-method.md)|元の UnorderedMapView オブジェクトを 2 つの UnorderedMapView オブジェクトに分割します。|  
  
## 継承階層  
 `UnorderedMapView`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)