---
title: COMM |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 111dac47089fea13febe787e5b73557b287beea8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
---
# <a name="comm"></a>COMM
指定された属性を持つ土台変数を作成`definition`です。  
  
## <a name="syntax"></a>構文  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>コメント  
 各`definition`は次の形式があります。  
  
 [[*langtype*]] [[**NEAR** &#124; **FAR**]] *label ***:**`type`[[**:*** count*]]  
  
 *ラベル*変数の名前を指定します。 `type`任意の型指定子を指定できます ([バイト](../../assembler/masm/byte-masm.md)、 [WORD](../../assembler/masm/word.md)など) またはバイト数を指定する整数。 *カウント*(1 つは、既定値) のデータ オブジェクトの数を指定します。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)