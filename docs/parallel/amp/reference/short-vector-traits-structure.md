---
title: "short_vector_traits 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::short_vector_traits"
dev_langs: 
  - "C++"
ms.assetid: cd9492da-9e02-4a6e-9d50-b61252cdb460
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# short_vector_traits 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

short\_vector\_traits は短いベクター型またはスカラー型の基になるベクターの長さとスカラー型の retrival できます。  
  
## 構文  
  
```  
template<  
   typename _Type  
>  
struct short_vector_traits;  
template<>  
struct short_vector_traits<unsigned int>;  
template<>  
struct short_vector_traits<uint_2>;  
template<>  
struct short_vector_traits<uint_3>;  
template<>  
struct short_vector_traits<uint_4>;  
template<>  
struct short_vector_traits<int>;  
template<>  
struct short_vector_traits<int_2>;  
template<>  
struct short_vector_traits<int_3>;  
template<>  
struct short_vector_traits<int_4>;  
template<>  
struct short_vector_traits<float>;  
template<>  
struct short_vector_traits<float_2>;  
template<>  
struct short_vector_traits<float_3>;  
template<>  
struct short_vector_traits<float_4>;  
template<>  
struct short_vector_traits<unorm>;  
template<>  
struct short_vector_traits<unorm_2>;  
template<>  
struct short_vector_traits<unorm_3>;  
template<>  
struct short_vector_traits<unorm_4>;  
template<>  
struct short_vector_traits<norm>;  
template<>  
struct short_vector_traits<norm_2>;  
template<>  
struct short_vector_traits<norm_3>;  
template<>  
struct short_vector_traits<norm_4>;  
template<>  
struct short_vector_traits<double>;  
template<>  
struct short_vector_traits<double_2>;  
template<>  
struct short_vector_traits<double_3>;  
template<>  
struct short_vector_traits<double_4>;  
```  
  
#### パラメーター  
 `_Type`  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`value_type`||  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[short\_vector\_traits::short\_vector\_traits コンストラクター](../Topic/short_vector_traits::short_vector_traits%20Constructor.md)||  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[short\_vector\_traits::size 定数](../Topic/short_vector_traits::size%20Constant.md)||  
  
## 継承階層  
 `short_vector_traits`  
  
## 必要条件  
 **ヘッダー:** amp\_short\_vectors.h  
  
 **名前空間:** Concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)