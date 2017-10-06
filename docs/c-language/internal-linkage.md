---
title: "内部リンケージ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 6d693f4d12fcfe048ef16d9eb8e8806a58d62030
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="internal-linkage"></a>内部リンケージ
オブジェクトまたは関数のファイル スコープ ID の宣言に *storage-class-specifier* **static** が含まれている場合、ID には内部リンケージがあります。 それ以外の場合、識別子は外部リンケージを持ちます。 非終端要素の *storage-class-specifier* の詳細については、「[ストレージ クラス](../c-language/c-storage-classes.md)」をご覧ください。  
  
 1 つの翻訳単位内では、内部リンケージを持つ識別子の各インスタンスは、同じ識別子または関数を表します。 内部リンク ID は 1 つの翻訳単位において一意です。  
  
## <a name="see-also"></a>関連項目  
 [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)
