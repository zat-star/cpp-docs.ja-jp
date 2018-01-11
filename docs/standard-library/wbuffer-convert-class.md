---
title: "wbuffer_convert クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocmon/stdext::cvt::wbuffer_convert
dev_langs: C++
helpviewer_keywords: wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cee0951401c43cb72d58bf7e9e61e4f4a89d6675
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wbufferconvert-class"></a>wbuffer_convert クラス
バイト ストリーム バッファーとの間の要素の転送を制御するストリーム バッファーを説明します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Codecvt`|変換オブジェクトを表す[ロケール](../standard-library/locale-class.md) ファセット。|  
|`Elem`|ワイド文字要素型。|  
|`Traits`|*Elem* と関連付けられている特徴。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、文字の特徴がクラス `Traits` によって記述される型 `_Elem` の要素の、型 `std::streambuf` のバイト ストリーム バッファーとの間での転送を制御するストリーム バッファーについて説明します。  
  
 `Elem` 値のシーケンスとマルチバイト シーケンスとの間の変換は、クラス `Codecvt<Elem, char, std::mbstate_t>` のオブジェクトによって実行されます。このことは、標準コード変換ファセット `std::codecvt<Elem, char, std::mbstate_t>` の要件を満たしています。  
  
 このテンプレート クラスのオブジェクトは、以下のものを格納します。  
  
-   基になるバイト ストリーム バッファーへのポインター  
  
-   割り当てられた変換オブジェクトへのポインター ([wbuffer_convert](../standard-library/wbuffer-convert-class.md) のときに解放される)
