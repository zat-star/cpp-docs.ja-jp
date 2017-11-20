---
title: "別のテーブルには、行への参照が含まれている場合は、列を更新します |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cac57f2f4a1175fa1d9f4009e10fd3d0fae2a3b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>行への参照が別のテーブルにある場合に列を更新する方法
一部のプロバイダーは、行の変更のどの列を検出できますが、多くのプロバイダーができません。 その結果、列の更新時に発生するエラーを更新しようとしている行への参照があります。 この問題を解決するには、変更する列のみを含む別のアクセサーを作成します。 アクセサーにはその数を渡す`SetData`です。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)