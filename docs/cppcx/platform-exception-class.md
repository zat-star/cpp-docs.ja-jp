---
title: "Platform::Exception クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Exception クラス"
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Exception クラス
アプリケーションの実行中に発生したエラーを表します。 カスタム例外クラスは、`Platform::Exception` から派生できません。 カスタム例外が必要な場合は、`Platform::COMException` を使用し、アプリケーション特有の HRESULT を指定できます。  
  
## 構文  
  
```cpp  
public ref class Exception : Object,    IException,    IPrintable,    IEquatable  
```  
  
## メンバー  
 `Exception` クラスは、`Object` クラス、および `IException`、`IPrintable`、および `IEquatable` の各インターフェイスから継承します。  
  
 `Exception` クラスには、次の種類のメンバーもあります。  
  
### コンストラクター  
  
|メンバー|説明|  
|----------|--------|  
|[Exception::Exception コンストラクター](../cppcx/exception-exception-constructor.md)|`Exception` クラスの新しいインスタンスを初期化します。|  
  
### メソッド  
 `Exception` クラスは、`Equals()` の `Finalize()`、`GetHashCode()`、`GetType()`、`MemberwiseClose()`、`ToString()`、および [Platform::Object クラス](../cppcx/platform-object-class.md) の各メソッドを継承します。`Exception` クラスには、次のメソッドもあります。  
  
|メンバー|説明|  
|----------|--------|  
|[Exception::CreateException メソッド](../cppcx/exception-createexception-method.md)|指定された HRESULT 値を表す例外を作成します。|  
  
### プロパティ  
 Exception クラスには、次のプロパティもあります。  
  
|メンバー|説明|  
|----------|--------|  
|[Exception::HResult プロパティ](../cppcx/exception-hresult-property.md)|例外に対応する HRESULT。|  
|[Exception::Message プロパティ](../cppcx/exception-message-property.md)|例外について説明するメッセージ。 この値は読み取り専用で、`Exception` が構築された後は変更できません。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)