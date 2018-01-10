---
title: "COMM |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COMM
dev_langs: C++
helpviewer_keywords: COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad12de948227f98ec73f779030b8e644dfad8b2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comm"></a>COMM
指定された属性を持つ土台変数を作成`definition`です。  
  
## <a name="syntax"></a>構文  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>コメント  
 各`definition`は次の形式があります。  
  
 [*langtype*] [**NEAR** &#124;です。**FAR**]*ラベル***:**`type`[**:***カウント*]  
  
 *ラベル*変数の名前を指定します。 `type`任意の型指定子を指定できます ([バイト](../../assembler/masm/byte-masm.md)、 [WORD](../../assembler/masm/word.md)など) またはバイト数を指定する整数。 *カウント*(1 つは、既定値) のデータ オブジェクトの数を指定します。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)