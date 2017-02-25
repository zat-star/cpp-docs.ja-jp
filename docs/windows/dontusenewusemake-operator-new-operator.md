---
title: "DontUseNewUseMake::operator new 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator new 演算子"
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# DontUseNewUseMake::operator new 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### パラメーター  
 `__unnamed0`  
 割り当てるためのメモリのバイト数を指定して作成できます。  
  
 `placement`  
 割り当てる型。  
  
## 戻り値  
 引数を渡す方法を `new`オーバーロードされた演算子提供します。  
  
## 解説  
 演算子をオーバーロードし、`new` します RuntimeClass で使用されることを示します。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [DontUseNewUseMake クラス](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)