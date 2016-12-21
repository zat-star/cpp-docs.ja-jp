---
title: "HStringReference::HStringReference コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::HStringReference コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HStringReference クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest],   
unsigned int len)  
       throw();  
  
    HStringReference(HStringReference&& other) throw();  
  
```  
  
#### パラメーター  
 `sizeDest`  
 前の HStringReference バッファーのサイズを指定するテンプレート パラメーター。  
  
 `str`  
 ワイド文字列への参照。  
  
 `len`  
 この操作で使用する `str` パラメーター バッファーの最大長。  `len` パラメーターが指定されていない場合、`str` 全体のパラメーターが使用されます。  `len` が `sizeDest`より大きい場合は、`len``sizeDest`は \-1 に設定されます。  
  
 `other`  
 HStringReference の別のオブジェクト。  
  
## 解説  
 最初のコンストラクターは、パラメーター `str`と同じサイズ、HStringReference オブジェクトを初期化します。  
  
 2 番目のコンストラクターは、パラメーター `len`してサイズの specifeid その HStringReference オブジェクトを初期化します。  
  
 3 番目のコンストラクターは `other`パラメーターの値に HStringReference オブジェクトを初期化し、`other` パラメーターを破棄します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HStringReference クラス](../windows/hstringreference-class.md)