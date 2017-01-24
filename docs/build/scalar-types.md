---
title: "スカラー型 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# スカラー型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データがどのように配置されていてもデータへのアクセスはできますが、パフォーマンスの低下を防ぐため \(または、その他さまざまな理由から\)、データは自然な境界に配置することをお勧めします。  列挙型 \(Enum\) は、定数整数であり、32 ビット整数として扱われます。  次の表は、型定義と、次のアライメント値を使用してアライメントする場合に推奨されるストレージを示しています。  
  
-   バイト型 \(Byte\) – 8 ビット  
  
-   ワード型 \(Word\) – 16 ビット  
  
-   ダブルワード型 \(Double Word\) – 32 ビット  
  
-   クワドワード型 \(Quad Word\) – 64 ビット  
  
-   オクタワード型 – 128 ビット  
  
|||||  
|-|-|-|-|  
|スカラー型|C データ型|ストレージ サイズ \(バイト単位\)|推奨アライメント|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**unsigned short**|2|Word|  
|**INT32**|**int、long**|4|ダブルワード型 \(Doubleword\)|  
|**UINT32**|**unsigned int、unsigned long**|4|ダブルワード型 \(Doubleword\)|  
|**INT64**|`__int64`|8|クワドワード型 \(Quadword\)|  
|**UINT64**|**unsigned \_\_int64**|8|クワドワード型 \(Quadword\)|  
|**FP32 \(単精度\)**|**float**|4|ダブルワード型 \(Doubleword\)|  
|**FP64 \(倍精度\)**|**double**|8|クワドワード型 \(Quadword\)|  
|**POINTER**|**\***|8|クワドワード型 \(Quadword\)|  
|`__m64`|**struct \_\_m64**|8|クワドワード型 \(Quadword\)|  
|`__m128`|**struct \_\_m128**|16|Octaword|  
  
## 参照  
 [型とストレージ](../build/types-and-storage.md)