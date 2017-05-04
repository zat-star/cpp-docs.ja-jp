---
title: "Exception::CreateException メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::CreateException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::CreateException メソッド"
ms.assetid: 70e72bb4-3fec-478d-af3d-9ec8762d2825
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::CreateException メソッド
指定した HRESULT 値から Platform::Exception^ を作成します。  
  
## 構文  
  
```cpp  
Exception^ CreateException(int32 hr)  
Exception^ CreateException(int32 hr, Platform::String^ message)  
```  
  
## パラメーター  
 hr  
 通常は COM メソッドを呼び出すことによって取得した HRESULT 値。 この値が 0 であり、S\_OK と等しい場合は、このメソッドは [Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md) をスローします。成功する COM メソッドが例外をスローすることはないからです。  
  
 message  
 エラーを説明する文字列。  
  
## 戻り値  
 エラー HRESULT を表す例外。  
  
## 解説  
 COM インターフェイスのメソッドに対する呼び出しなどから、返された HRESULT から例外を作成するには、このメソッドを使用します。 カスタム メッセージを表示するために、String^ パラメーターを受け取るオーバーロードを使用することもできます。  
  
 まれに HRESULT を含むことがある [Platform::COMException](../cppcx/platform-comexception-class.md) を作成する代わりに、厳密に型指定された例外を作成する CreateException を使用することを強くお勧めします。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)