---
title: "既定の名前空間 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "default_CPP"
dev_langs: 
  - "C++"
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# 既定の名前空間
`default` 名前空間は、[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) によってサポートされる組み込み型を範囲とします。  
  
## 構文  
  
```  
namespace default;  
```  
  
## メンバー  
 組み込み型はすべて、次のメンバーを継承します。  
  
|||  
|-|-|  
|[default::\(type\_name\)::Equals メソッド](../cppcx/default-type-name-equals-method.md)|指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。|  
|[default::\(type\_name\)::GetHashCode メソッド](../cppcx/default-type-name-gethashcode-method.md)|このインスタンスのハッシュ コードを返します。|  
|[default::\(type\_name\)::GetType メソッド](../cppcx/default-type-name-gettype-method.md)|現在の型を表す文字列を返します。|  
|[default::\(type\_name\)::ToString メソッド](../cppcx/default-type-name-tostring-method.md)|現在の型を表す文字列を返します。|  
  
### 組み込み型  
  
|名前|説明|  
|--------|--------|  
|`char16`|Unicode \(UTF\-16\) コード ポイントを表す 16 ビットの数字以外の値。|  
|`float32`|32 ビットの IEEE 754 浮動小数点数。|  
|`float64`|64 ビットの IEEE 754 浮動小数点数。|  
|`int16`|16 ビット符号付き整数。|  
|`int32`|32 ビット符号付き整数。|  
|`int64`|64 ビット符号付き整数。|  
|`int8`|8 ビット符号付き数値。|  
|`uint16`|16 ビット符号なし整数。|  
|`uint32`|32 ビット符号なし整数|  
|`uint64`|64 ビット符号なし整数。|  
|`uint8`|8 ビット符号なし数値。|  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)