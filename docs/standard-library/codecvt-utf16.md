---
title: "codecvt_utf16 | Microsoft Docs"
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
  - "codecvt/std::codecvt_utf16"
  - "std::codecvt_utf16"
  - "std.codecvt_utf16"
  - "codecvt_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf16 クラス"
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

表す、 [ロケール](../standard-library/locale-class.md) ワイド文字の ucs\-2 または ucs\-4 としてエンコードし、UTF 16LE または UTF 16BE としてエンコードされたバイト ストリーム間で変換されるファセット。  
  
## 構文  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Elem`|ワイド文字要素型。|  
|`Maxcode`|ロケールのファセットの文字の最大数。|  
|`Mode`|ロケールのファセットの構成情報。|  
  
## 解説  
 場合に、このテンプレート クラスがワイド文字の ucs\-2 または ucs\-4 としてエンコードと UTF 16LE、としてエンコードされたバイト ストリーム間で変換 `Mode & little_endian`, 、または UTF 16BE それ以外の場合。  
  
 バイナリ ファイルに書き込まれるバイト ストリームテキスト ファイルに記述されている場合、破損していることができます。  
  
## 必要条件  
 **ヘッダー:** \< codecvt \>  
  
 **名前空間:** std