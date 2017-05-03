---
title: "Platform::Collections::Vector クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector クラス (C++/Cx)"
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 17
---
# Platform::Collections::Vector クラス
インデックスによって個別にアクセスできるオブジェクトのシーケンシャル コレクションを表します。  
  
## 構文  
  
```  
template <typename T, typename E>  
   ref class Vector sealed;  
```  
  
#### パラメーター  
 `T`  
 Vector オブジェクトに含まれている要素の型。  
  
 `E`  
 `T` 型の値との等値性をテストするための二項述語を指定します。 既定値は `std::equal_to<T>` です。  
  
## 解説  
 使用できる型は次のとおりです。  
  
1.  整数  
  
2.  インターフェイス クラス ^  
  
3.  パブリック ref クラス ^  
  
4.  value struct  
  
5.  パブリック列挙型クラス  
  
 Vector クラスは、[Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) インターフェイスに関する C\+\+ の具象実装です。  
  
 パブリックの戻り値またはパラメーターで Vector 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 このエラーを修正するには、パラメーターまたは戻り値の型を [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) に変更します。 詳細については、「[Collections \(C\+\+\/CX\) \(コレクション \(C\+\+\/CX\)\)](../cppcx/collections-c-cx.md)」を参照してください。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Vector::Vector コンストラクター](../cppcx/vector-vector-constructor.md)|ベクター クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[Vector::Append メソッド](../cppcx/vector-append-method.md)|指定された項目を、現在の Vector の最後の項目の後に挿入します。|  
|[Vector::Clear メソッド](../cppcx/vector-clear-method.md)|現在のベクター内のすべての要素を削除します。|  
|[Vector::First メソッド](../cppcx/vector-first-method.md)|Vector 内の最初の要素を指定する反復子を返します。|  
|[Vector::GetAt メソッド](../cppcx/vector-getat-method.md)|指定されたインデックスで識別される現在のベクターの要素を取得します。|  
|[Vector::GetMany メソッド](../cppcx/vector-getmany-method.md)|指定されたインデックスを開始位置として、現在の Vector から項目のシーケンスを取得します。|  
|[Vector::GetView メソッド](../cppcx/vector-getview-method.md)|ベクターの読み取り専用ビュー、つまり [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) を返します。|  
|[Vector::IndexOf メソッド](../cppcx/vector-indexof-method.md)|現在のベクター内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。|  
|[Vector::InsertAt メソッド](../cppcx/vector-insertat-method.md)|指定されたインデックスによって識別される要素の後の現在のベクターに、指定された項目を挿入します。|  
|[Vector::ReplaceAll メソッド](../cppcx/vector-replaceall-method.md)|現在のベクターの要素を削除し、指定された配列の要素を挿入します。|  
|[Vector::RemoveAt メソッド](../cppcx/vector-removeat-method.md)|現在のベクターから指定されたインデックスで識別される要素を削除します。|  
|[Vector::RemoveAtEnd メソッド](../cppcx/vector-removeatend-method.md)|現在の Vector の末尾から要素を削除します。|  
|[Vector::SetAt メソッド](../cppcx/vector-setat-method.md)|現在の Vector で、指定されたインデックスによって識別される要素に、指定された値を割り当てます。|  
|[Vector::Size メソッド](../cppcx/vector-size-method.md)|現在のベクター オブジェクトの要素数を返します。|  
  
### イベント  
  
|||  
|-|-|  
|名前|説明|  
|イベント [Windows::Foundation::Collection::VectorChangedEventHandler\<T\>^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Vector が変更されたときに発生します。|  
  
## 継承階層  
 `Vector`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) Platform 名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)