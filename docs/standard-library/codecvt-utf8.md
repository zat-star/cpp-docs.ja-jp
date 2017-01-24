---
title: "codecvt_utf8 | Microsoft Docs"
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
  - "std.codecvt_utf8"
  - "std::codecvt_utf8"
  - "codecvt_utf8"
  - "codecvt/std::codecvt_utf8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8 クラス"
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

UCS\-2 としてエンコードされるワイド文字または UCS\-4 との間で変換を行うと、UTF\-8 としてエンコードされるバイト ストリームを表します [ロケール](../standard-library/locale-class.md) のファセット。  
  
## 構文  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Elem`|ワイド文字の要素型。|  
|`Maxcode`|ロケールのファセットの最大文字数。|  
|`Mode`|ロケールのファセットの構成情報。|  
  
## 解説  
 バイト ストリームはバイナリ ファイルまたはテキスト ファイルに書き込むことができます。  
  
## 必要条件  
 **ヘッダー:** の \<codecvt\>  
  
 **名前空間:** std