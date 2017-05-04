---
title: "Platform::Object クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Object クラス"
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Object クラス
Windows ストア アプリ内で ref クラスと ref 構造体に対して共通の動作を提供します。 ref クラスと ref 構造体のインスタンスは、いずれも Platform::Object^ に暗黙的に変換可能で、仮想の ToString メソッドをオーバーライドできます。  
  
## 構文  
  
```scr  
public ref class Object : Object  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Object::Object コンストラクター](../cppcx/object-object-constructor.md)|Object クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[Object::Equals メソッド](../cppcx/object-equals-method.md)|指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。|  
|[Object::GetHashCode メソッド](../cppcx/object-gethashcode-method.md)|このインスタンスのハッシュ コードを返します。|  
|[Object::ReferenceEquals メソッド](../cppcx/object-referenceequals-method.md)|指定された Object インスタンスが同一のインスタンスかどうかを判断します。|  
|[ToString メソッド](../cppcx/object-tostring-method-c-cx.md)|現在のオブジェクトを表す文字列を返します。 オーバーライドできます。|  
|[GetType メソッド](../cppcx/object-gettype-method.md)|現在のインスタンスを記述する [Platform::Type](../cppcx/platform-type-class.md) を取得します。|  
  
## 継承階層  
 `Object`  
  
 `Object`  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [\(NOTINBUILD\) プラットフォーム名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)