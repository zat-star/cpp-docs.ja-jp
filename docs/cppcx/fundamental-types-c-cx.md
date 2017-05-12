---
title: "基本的な型 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c9f82907-25f2-440b-91d6-afb8dbd46ea6
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 14
---
# 基本的な型 (C++/CX)
標準的な C\+\+ 組み込み型の他に、[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) は、標準 C\+\+ 型にマップする [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 基本型の typedefs を提供することによって、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アーキテクチャによって定義される型システムをサポートしています。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、ブール値、文字、数値の基本型を実装しています。 これらの typedefs は、`default` 名前空間 \(明示的に指定する必要はない\) で定義されます。 加えて、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、特定の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型およびインターフェイスにラッパーと具体的な実装を提供します。  
  
## ブール値および文字の種類  
 組み込みブール値と文字型、および標準 C\+\+ に相当するものを次の表に一覧表示します。  
  
|名前空間|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 名|定義|標準 C\+\+ 名|値の範囲|  
|----------|--------------------------------------------------------------------|--------|----------------|----------|  
|プラットフォーム|ブール型|8 ビットのブール値。|bool|`true` \(0 以外\) と `false` \(0\)|  
|default|char16|Unicode \(UTF\-16\) コード ポイントを表す 16 ビットの数字以外の値。|wchar\_t<br /><br /> または<br /><br /> L'c'|\(Unicode 標準によって指定される\)|  
  
## 数値型  
 組み込み数値型を次の表に一覧表示します。 数値型は `default` 名前空間で宣言され、対応する C\+\+ 組み込み型の typedefs です。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ではサポートされていない C\+\+ 組み込み型もあります \(long など\)。 コードを一貫性のあるものとし、わかりやすくするために、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 名を使用することをお勧めします。  
  
|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 名|定義|標準 C\+\+ 名|値の範囲|  
|--------------------------------------------------------------------|--------|----------------|----------|  
|int8|8 ビット符号付き数値。|signed char|–128 ～ 127|  
|uint8|8 ビット符号なし数値。|unsigned char|0 ～ 255|  
|int16|16 ビット符号付き整数。|short|–32,768 ～ 32,767|  
|uint16|16 ビット符号なし整数。|unsigned short|0 ～ 65,535|  
|int32|32 ビット符号付き整数。|int|–2,147,483,648 ～ 2,147,483,647|  
|uint32|32 ビット符号なし整数。|unsigned int|0 ～ 4,294,967,295|  
|int64|64 ビット符号付き整数。|long long \-または\- \_\_int64|–9,223,372,036,854, 775,808 ～ 9,223,372,036,854,775,807|  
|uint64|64 ビット符号なし整数。|符号なし long long \-または\- 符号なし \_\_int64|0 ～ 18,446,744,073,709,551,615|  
|float32|32 ビットの IEEE 754 浮動小数点数。|float|3.4E \+\/\- 38 \(7 桁\)|  
|float64|64 ビットの IEEE 754 浮動小数点数。|double|1.7E \+\/\- 308 \(15 桁\)|  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アーキテクチャによって定義され、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] に組み込まれるいくつかの追加の型を次の表に一覧表示します。 オブジェクトと文字列は参照型です。 それ以外は値型です。 型はすべて、`Platform` 名前空間で宣言されています。 完全なリストについては、[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md) を参照してください。  
  
|名前|定義|  
|--------|--------|  
|オブジェクト|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型を表します。|  
|String|テキストを表す一連の文字。|  
|Rect|四角形の位置とサイズを表す 4 つ浮動小数点数のセット。|  
|SizeT|高さと幅を指定する浮動小数点数の順序付きペア。|  
|ポイント|2 次元プレートの位置を定義する浮動小数点の x 座標と y 座標の順序付きペア。|  
|Guid|一意の識別子として使用される 128 ビットの数値以外の値。|  
|UIntPtr|\(内部使用のみ。\) ポインターとして使用される符号なし 64 ビット値。|  
|IntPtr|\(内部使用のみ。\)  ポインターとして使用される符号付き 64 ビット値。|  
  
## 参照  
 [型システム](../cppcx/type-system-c-cx.md)