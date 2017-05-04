---
title: "Platform::IntPtr 値クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IntPtr 構造体"
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::IntPtr 値クラス
サイズがプラットフォームに特有の \(32 ビットまたは 64 ビット\)、符号付きポインターまたはハンドルを表します。  
  
## 構文  
  
```cpp  
public value struct IntPtr  
```  
  
## メンバー  
 IntPtr には、次のメンバーがあります。  
  
|メンバー|説明|  
|----------|--------|  
|[IntPtr::IntPtr コンストラクター](../cppcx/intptr-intptr-constructor.md)|IntPtr の新しいインスタンスを初期化します。|  
|[IntPtr::op\_explicit 演算子](../cppcx/intptr-op-explicit-operator.md)|指定されたパラメーターを IntPtr、または IntPtr 値へのポインターに変換します。|  
|[IntPtr::ToInt32 メソッド](../cppcx/intptr-toint32-method.md)|現在の IntPtr を 32 ビット整数に変換します。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)