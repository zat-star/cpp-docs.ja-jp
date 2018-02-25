---
title: "別のテーブルには、行への参照が含まれている場合は、列を更新します |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5b4d4c041e1a6ad0f40107ef2bfb71293c05e5d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>行への参照が別のテーブルにある場合に列を更新する方法
一部のプロバイダーは、行の変更のどの列を検出できますが、多くのプロバイダーができません。 その結果、列の更新時に発生するエラーを更新しようとしている行への参照があります。 この問題を解決するには、変更する列のみを含む別のアクセサーを作成します。 アクセサーにはその数を渡す`SetData`です。  
  
## <a name="see-also"></a>参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)