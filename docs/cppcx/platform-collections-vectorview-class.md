---
title: "Platform::Collections::VectorView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView クラス"
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Platform::Collections::VectorView クラス
インデックスによって個別にアクセスできるオブジェクトのシーケンシャル コレクションの読み取り専用ビューを表します。 コレクション内の各オブジェクトの型は、テンプレート パラメーターによって指定されます。  
  
## 構文  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### パラメーター  
 `T`  
 `VectorView` オブジェクトに格納されている要素の型。  
  
 `E`  
 `T` 型の値との等値性をテストするための二項述語を指定します。 既定値は `std::equal_to<T>` です。  
  
## 解説  
 `VectorView` クラスは、[Windows::Foundation::Collections::IVectorView\<T\>](http://go.microsoft.com/fwlink/p/?LinkId=262411) インターフェイスと、標準テンプレート ライブラリの反復子のサポートを実装します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[VectorView::VectorView コンストラクター](../cppcx/vectorview-vectorview-constructor.md)|VectorView クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[VectorView::First メソッド](../cppcx/vectorview-first-method.md)|VectorView 内の最初の要素を指定する反復子を返します。|  
|[VectorView::GetAt メソッド](../cppcx/vectorview-getat-method.md)|指定されたインデックスで示される現在の VectorView の要素を取得します。|  
|[VectorView::GetMany メソッド](../cppcx/vectorview-getmany-method.md)|指定されたインデックスを開始位置として、現在の VectorView から項目のシーケンスを取得します。|  
|[VectorView::IndexOf メソッド](../cppcx/vectorview-indexof-method.md)|現在の VectorView 内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。|  
|[VectorView::Size メソッド](../cppcx/vectorview-size-method.md)|現在の VectorView オブジェクトの要素数を返します。|  
  
## 継承階層  
 `VectorView`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) プラットフォーム名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)