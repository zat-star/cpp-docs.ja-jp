---
title: "動的オブジェクトの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 755cbf614966ad6faedbe8db9bbf11ac88c63328
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dynamic-object-creation"></a>オブジェクトの動的生成
この記事では、実行時に動的にオブジェクトを作成する方法について説明します。 プロシージャは、記事で説明したようにランタイム クラス情報を使用して[クラス情報にアクセスする](../mfc/accessing-run-time-class-information.md)です。  
  
#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>ランタイム クラスを指定してオブジェクトを動的に作成するには  
  
1.  使用してオブジェクトを動的に作成する次のコードを使用して、`CreateObject`の関数、`CRuntimeClass`です。 失敗した場合、なお`CreateObject`返します**NULL**例外を生成する代わりに。  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]  
  
## <a name="see-also"></a>参照  
 [CObject の使い方](../mfc/using-cobject.md)

