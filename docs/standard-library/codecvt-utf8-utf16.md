---
title: "codecvt_utf8_utf16 | Microsoft Docs"
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
  - "codecvt_utf8_utf16"
  - "codecvt/std::cvt_utf8_utf16"
  - "std::codecvt_utf8_utf16"
  - "std.codecvt_utf8_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8_utf16 クラス"
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

UTF\-16 としてエンコードされるワイド文字と UTF\-8 としてエンコードされるバイト ストリームの間で変換を行う [ロケール](../standard-library/locale-class.md) のファセットを表します。  
  
## 構文  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>  
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