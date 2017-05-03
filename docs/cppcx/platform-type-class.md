---
title: "Platform::Type クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Type クラス"
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Type クラス
型に関するランタイム情報 \(文字列名と型コード\) を含みます。 任意のオブジェクトで [Object::GetType メソッド](../cppcx/object-gettype-method.md)を呼び出すか、クラスまたは構造体名で [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) 演算子を使用して取得されます。  
  
## 構文  
  
```cpp  
public ref class Platform::Type :      Platform::Object,      Platform::Details::IEquatable,      Platform::Details::IPrintable  
```  
  
## 解説  
 `Type` クラスは、オブジェクトの実行時の型に基づいて分岐する `if` ステートメントまたは `switch` ステートメントを使用して処理を指示する必要があるアプリケーションで役に立ちます。 型のカテゴリを記述する型コードは [Type::GetTypeCode メソッド](../cppcx/type-gettypecode-method.md) メンバー関数を使用して取得されます。  
  
## パブリック メソッド  
  
|||  
|-|-|  
|[Type::GetTypeCode メソッド](../cppcx/type-gettypecode-method.md)|オブジェクトの [Platform::TypeCode 列挙](../cppcx/platform-typecode-enumeration.md)値を返します。|  
  
## パブリック プロパティ  
  
|||  
|-|-|  
|[Type::FullName プロパティ](../cppcx/type-fullname-property.md)|返します、 [platform::string Class](../cppcx/platform-string-class.md)^ 型の完全修飾名を表し、を使用している。   。\(ドット\) を区切り記号としてできません:: \(二重のコロン\) など、"MyNamespace.MyClass"です。|  
  
## 変換演算子  
  
|||  
|-|-|  
|[Type^ 演算子](../cppcx/operator-subtracttype-hat.md)|`Windows::UI::Xaml::Interop::TypeName` から `Platform::Type` への変換を有効にします。|  
|[Windows::UI::Xaml::Interop::TypeName 演算子](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)|`Platform::Type` から `Windows::UI::Xaml::Interop::TypeName` への変換を有効にします。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)