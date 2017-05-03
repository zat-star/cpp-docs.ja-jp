---
title: "Platform::DisconnectedException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::DisconnectedException"
  - "Platform/Platform::DisconnectedException::DisconnectedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::DisconnectedException"
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::DisconnectedException クラス
存在しなくなった COM サーバーを COM プロキシ オブジェクトが参照しようとするとスローされます。  
  
## 構文  
  
```  
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## 解説  
 クラス A が別のプロセスにある他のクラス \(クラス B\) を参照している場合、クラス A には、クラス B を保持するプロセス外の COM サーバーと通信するプロキシ オブジェクトが必要になります。サーバーがメモリ不足になってもクラス A が認識しないことがあります。 この場合、例外 RPC\_E\_DISCONNECTED はスローされ、Platform::DisconnectedException に変換されます。 これが発生する 1 つのシナリオは、イベント ソースに渡されたデリゲートをイベント ソースが呼び出したものの、イベントをサブスクライブした後のある時点でデリゲートが破棄された場合です。 この場合、イベント ソースは、呼び出しリストからそのデリゲートを削除します。  
  
 詳細については、[COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)