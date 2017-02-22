---
title: "基本型の格納 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "算術演算 [C++], 型"
  - "データ型 [C], 指定子"
  - "データ型 [C], ストレージ"
  - "Double 型, ストレージ"
  - "浮動小数点数, ストレージ"
  - "int データ型"
  - "整数型"
  - "整数型, ストレージ"
  - "long double キーワード [C], ストレージ"
  - "long キーワード [C]"
  - "short データ型"
  - "signed 型 [C++], ストレージ"
  - "指定子 [C++], 型"
  - "ストレージ [C++], 型"
  - "型の格納 [C++]"
  - "型指定子 [C++], サイズ"
  - "型 [C], 算術"
  - "unsigned 型 [C++], ストレージ"
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 基本型の格納
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は、各基本型に関連付けられたストレージをまとめたものです。  
  
### 基本型のサイズ  
  
|型|ストレージ|  
|-------|-----------|  
|`char`、`unsigned char`、**signed char**|1 バイト|  
|**short**、**unsigned short**|2 バイト|  
|`int`, `unsigned int`|4 バイト|  
|**long**、`unsigned long`|4 バイト|  
|**float**|4 バイト|  
|**double**|8 バイト|  
|`long double`|8 バイト|  
  
 C のデータ型は一般カテゴリに分類されます。  "整数型" には、`char`、`int`、**short**、**long**、**signed**、`unsigned`、および `enum` が含まれます。  "浮動小数点型" には、**float**、**double**、および `long double` が含まれます。  "数値型" には、すべての浮動小数点型と整数型が含まれます。  
  
## 参照  
 [型の宣言](../c-language/declarations-and-types.md)