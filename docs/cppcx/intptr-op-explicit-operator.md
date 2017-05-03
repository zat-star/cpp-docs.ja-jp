---
title: "IntPtr::op_explicit 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr::op_explicit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntPtr::op_explicit メソッド"
ms.assetid: cc52e9d5-fe73-471b-8cff-d9f684ba6e20
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# IntPtr::op_explicit 演算子
指定されたパラメーターを IntPtr、または IntPtr 値へのポインターに変換します。  
  
## 構文  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
#### パラメーター  
 value1  
 ハンドルまたは IntPtr へのポインター。  
  
 value2  
 IntPtr に変換できる 32 ビット整数。  
  
 value3  
 IntPtr。  
  
## 戻り値  
 1 番目と 2 番目の演算子は IntPtr を返します。 3 番目の演算子は、現在の IntPtr によって表される値へのポインターを返します。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::IntPtr 値クラス](../cppcx/platform-intptr-value-class.md)