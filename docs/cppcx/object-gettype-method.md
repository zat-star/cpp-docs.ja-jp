---
title: "Object::GetType メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetType"
ms.assetid: f633d71a-ff80-49f9-931d-189c00b1f6c5
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::GetType メソッド
オブジェクトのランタイムの型を記述する [Platform::Type](../cppcx/platform-type-class.md) オブジェクトを返します。  
  
## 構文  
  
```vb  
Object::GetType()  
```  
  
```csharp  
  
```  
  
## プロパティ値\/戻り値  
 オブジェクトのランタイムの型を記述する [Platform::Type](../cppcx/platform-type-class.md) オブジェクト。  
  
## 解説  
 静的な [Type::GetTypeCode メソッド](../cppcx/type-gettypecode-method.md) を使用して、現在の型を表す [Platform::TypeCode 列挙型](../cppcx/platform-typecode-enumeration.md) 値を取得できます。 これは主に、組み込み型に使用できます。[Platform::String](../cppcx/platform-string-class.md) 以外の ref クラスの型コードは、Object \(1\) です。  
  
 [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) クラスは、言語に依存せずに Windows のコンポーネントとアプリとの間で型情報をやり取りする方法として、Windows API で使用されます。 T[Platform::Type クラス](../cppcx/platform-type-class.md) には、`Type` と `TypeName` との間の変換を行う演算子があります。  
  
 XAML ページ間を移動するときなど、[typeid](http://msdn.microsoft.com/library/e9706cae-e7c4-4d6d-b474-646d73df3e70) 演算子を使用してクラス名の `Platform::Type` オブジェクトを返します。  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## 参照  
 [Platform::Type クラス](../cppcx/platform-type-class.md)   
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)   
 [型システム](../cppcx/type-system-c-cx.md)