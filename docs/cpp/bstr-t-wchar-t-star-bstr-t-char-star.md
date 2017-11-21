---
title: "_bstr_t::wchar_t *、_bstr_t::char * |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
dev_langs: C++
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c078b727c42bb4704cfc3867cc22592f49a63e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t*、_bstr_t::char*
**Microsoft 固有の仕様**  
  
 BSTR 文字をナロー文字配列またはワイド文字配列として返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      operator const wchar_t*( ) const throw( );   
operator wchar_t*( ) const throw( );   
operator const char*( ) const;   
operator char*( ) const;  
```  
  
## <a name="remarks"></a>コメント  
 これらの演算子は `BSTR` オブジェクトによってカプセル化された文字データを抽出するために使用できます。 返されたポインターに新しい値を割り当てると、元の BSTR データは変更されません。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)