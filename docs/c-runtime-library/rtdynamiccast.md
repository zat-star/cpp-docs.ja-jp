---
title: "__RTDynamicCast | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__RTDynamicCast"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__RTDynamicCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__RTDynamicCast"
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __RTDynamicCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[dynamic\_cast](../cpp/dynamic-cast-operator.md) の演算子のランタイムの実装。  
  
## 構文  
  
```cpp  
PVOID __RTDynamicCast (  
   PVOID inptr,   
   LONG VfDelta,  
   PVOID SrcType,  
   PVOID TargetType,   
   BOOL isReference  
   ) throw(...)  
```  
  
#### パラメーター  
 `inptr`  
 ポリモーフィック オブジェクトへのポインター。  
  
 `VfDelta`  
 オブジェクトの仮想関数ポインターのオフセット。  
  
 `SrcType`  
 `inptr` パラメーターが指すオブジェクトの静的な型。  
  
 `TargetType`  
 キャストで目的の結果。  
  
 `isReference`  
 型が参照である場合は`true` ; 型がポインターである場合 `false`。  
  
## 戻り値  
 正常終了した場合は、適切なサブオブジェクトへのポインター、; それ以外の場合は NULL。  
  
## 例外  
 `dynamic_cast<>` への入力が参照およびキャストの場合`bad_cast()` は失敗します。  
  
## 解説  
 型 `TargetType`オブジェクトに `inptr` を変換します。  `inptr` の型は、`TargetType` がポインターの場合はポインター、`TargetType` が参照の場合は左辺値である必要があります。  `TargetType` は、あらかじめ定義したクラス型へのポインターまたは参照を、無効にするポインターである必要があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|\_\_RTDynamicCast|rtti.h|