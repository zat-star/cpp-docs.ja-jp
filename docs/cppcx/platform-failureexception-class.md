---
title: "Platform::FailureException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::FailureException::FailureException"
  - "Platform/Platform::FailureException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::FailureException"
ms.assetid: 1729cd07-bfc2-448e-9db5-185d5cbf5b81
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::FailureException クラス
操作が失敗したときにスローされます。 これは E\_FAIL HRESULT と同等です。  
  
## 構文  
  
```cpp  
public ref class FailureException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## コメント  
 詳細については、[COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)