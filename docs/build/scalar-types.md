---
title: "スカラー型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15b0915637025e176ee98d01be3991b30b4e6544
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="scalar-types"></a>スカラー型
データへのアクセスは、どのように配置されてによって生じることができます、データが、パフォーマンスが失われる (やさまざまな理由) を回避する自然な境界に合わせて調整することをお勧めします。 列挙型が定数の整数であり、32 ビット整数値として扱われます。 次の表の種類の定義と推奨される記憶域を次のアラインメント値を使用して配置に関連します。  
  
-   バイトの 8 ビット  
  
-   Word の 16 ビット  
  
-   ダブル ワード - 32 ビット  
  
-   クアッド ワード - 64 ビット  
  
-   オクタワード - 128 ビット  
  
|||||  
|-|-|-|-|  
|スカラー型|C データ型|ストレージ サイズ (バイト単位)|推奨される配置|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16 型**|**short**|2|Word|  
|**UINT16 型**|**unsigned short**|2|Word|  
|**INT32**|**int、long**|4|ダブルワード|  
|**UINT32**|**符号なし int、unsigned long**|4|ダブルワード|  
|**INT64**|`__int64`|8|Quadword|  
|**UINT64**|**unsigned __int64**|8|Quadword|  
|**FP32 (1 つの有効桁数)**|**float**|4|ダブルワード|  
|**FP64 (有効桁数を 2 つ)**|**double**|8|Quadword|  
|**ポインター**|**\***|8|Quadword|  
|`__m64`|**構造体 _ _m64**|8|Quadword|  
|`__m128`|**_ _m128 の構造体**|16|Octaword|  
  
## <a name="see-also"></a>参照  
 [型とストレージ](../build/types-and-storage.md)