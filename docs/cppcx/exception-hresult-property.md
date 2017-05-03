---
title: "Exception::HResult プロパティ | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::HResult プロパティ"
ms.assetid: 24ef008d-6884-4b8b-9556-41bfa6e1edf1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::HResult プロパティ
例外に対応する HRESULT。  
  
## 構文  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## プロパティ値  
 HRESULT 値。  
  
## 解説  
 ほとんどの例外は、HRESULT 値の形で返される COM エラーとして開始されます。 C\+\+\/CX はこれらの値を Platform::Exception^ オブジェクトに変換し、このプロパティは元のエラー コードの値を格納します。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::Exception クラス](../cppcx/platform-exception-class.md)