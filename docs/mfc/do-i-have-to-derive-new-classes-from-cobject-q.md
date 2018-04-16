---
title: "CObject から新しくクラスを派生する必要性 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c485bba4d62d279b0f17b887080284940a8bbdd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject から新しくクラスを派生する必要性
必要はありません。  
  
 クラスを派生[CObject](../mfc/reference/cobject-class.md) 、用意されているシリアル化やダイナミック creatability などの機能を必要とします。 多くの場合、それらから派生することをお勧めようにファイルにシリアル化する必要があるデータ クラスの多く`CObject`です。 派生したクラスの例の`CObject`を参照してください、 [Scribble サンプル](../visual-cpp-samples.md)です。  
  
## <a name="see-also"></a>参照  
 [CObject クラス: Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)
