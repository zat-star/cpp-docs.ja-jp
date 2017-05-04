---
title: "Platform::ChangedStateException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ChangedStateException"
  - "Platform/Platform::ChangedStateException::ChangedStateException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ChangedStateException"
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ChangedStateException クラス
オブジェクトの内部状態が変化したときにスローされ、メソッドの結果を無効にします。  
  
## 構文  
  
```cpp  
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## コメント  
 この例外がスローされる 1 つの例は、コレクション反復子またはコレクション ビューのメソッドが、親コレクションの変更後に呼び出された場合です。この結果、メソッドの結果は無効になります。  
  
 詳細については、[COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)