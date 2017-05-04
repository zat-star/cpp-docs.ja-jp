---
title: "Exception::Exception コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::Exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::Exception コンストラクター"
ms.assetid: 173b434e-e3a8-41f5-904e-0e8fc0f21950
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::Exception コンストラクター
Exception クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
  
Exception(int32 hresult)  
Exception(int32 hresult, ::Platform::String^ message)  
```  
  
#### パラメーター  
 `hresult`  
 例外で表されるエラー HRESULT。  
  
 `message`  
 例外に関連付けられているユーザー指定のメッセージ \(規範的テキストなど\)。 一般に、エラーが発生した方法と理由についてできるだけ具体的に説明するメッセージを提供する、2 番目のオーバーロードを優先する必要があります。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)