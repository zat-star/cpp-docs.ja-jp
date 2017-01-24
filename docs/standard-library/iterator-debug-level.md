---
title: "_ITERATOR_DEBUG_LEVEL | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ITERATOR_DEBUG_LEVEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ITERATOR_DEBUG_LEVEL"
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
caps.latest.revision: 6
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ITERATOR_DEBUG_LEVEL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_ITERATOR_DEBUG_LEVEL` \(IDL\) マクロは [\_SECURE\_SCL](../standard-library/secure-scl.md) \(SCL\) と [\_HAS\_ITERATOR\_DEBUGGING](../Topic/_HAS_ITERATOR_DEBUGGING.md) \(非表示\) マクロの機能により、または結合します。  
  
## マクロの値  
 次の表は、値が `_ITERATOR_DEBUG_LEVEL` マクロでどのように使用代わられるまたは `_SECURE_SCL` と `_HAS_ITERATOR_DEBUGGING` マクロの値を、最後について説明します。  
  
 以下のセクションでは SCL と非表示のマクロの値について説明します。  
  
 SCL\=0  
 無効に反復子をチェックします。  
  
 SCL\=1  
 PInvoke は、反復子をチェックします。  
  
 HID\=0  
 デバッグ ビルドの反復子のデバッグを無効にします。  
  
 HID\=1  
 デバッグ ビルドの反復子のデバッグを有効にします。  リリース ビルドの HID 有効にできません。  
  
 IDL マクロの値が SCL と非表示のマクロ値に代わる方法を次の表に示します。  
  
|コンパイル モード|新しいマクロ|古いマクロ|説明|  
|---------------|------------|-----------|--------|  
|**デバッグ**||||  
||IDL\=0|SCL\=0、HID\=0|無効に反復子をチェックし、反復子のデバッグを無効にします。|  
||IDL\=1|SCL\=1、HID\=0|PInvoke は、反復子をチェックし、反復子のデバッグを無効にします。|  
||IDL\=2 \(既定\)|SCL\= \(適用されません\)、HID\=1|既定で、有効の反復子のデバッグ; チェックを行う反復子とは無関係です。|  
|**リリース**||||  
||IDL\=0 \(既定\)|SCL\=0|既定で、無効に反復子をチェックします。|  
||IDL\=1|SCL\=1|PInvoke は、反復子をチェック アウトした; 反復子のデバッグは関連していません。|  
  
## 解説  
 リリース モードでは、エラーが IDL\=2.を指定すると表示されます。  
  
 `_SECURE_SCL` と `_HAS_ITERATOR_DEBUGGING` マクロに似た機能をサポートするため、特定の状況で使用されるマクロおよびマクロの値は、ユーザーは不確定です。  この問題を解決するために、`_ITERATOR_DEBUG_LEVEL` マクロのみ使用することをお勧めします。  
  
## 参照  
 [安全なライブラリ: C\+\+ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)