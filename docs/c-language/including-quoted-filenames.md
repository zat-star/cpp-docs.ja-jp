---
title: "引用符で囲まれたファイル名を含む | Microsoft Docs"
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
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 70b5e68fc8a3c0c23b291220e4faf387e9aa11c2
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="including-quoted-filenames"></a>引用符で囲まれたファイル名を含む
**ANSI 3.8.2** インクルード可能なソース ファイルの引用された名前のサポート  
  
 2 組の二重引用符 (" ") 間にインクルード ファイルのあいまいでない完全なパスを指定すると、プリプロセッサはそのパスのみを検索し、標準ディレクトリを無視します。  
  
 [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec" に指定されたインクルード ファイルでは、ディレクトリの検索は親ファイルのディレクトリから始まり、その後にすべての祖父母ファイルのディレクトリが検索されます。 したがって、検索は現在処理中のソース ファイルが含まれるディレクトリに対して相対的に開始されます。 親の親ファイルが存在せず、見つからなかった場合は、ファイル名が山かっこで囲まれているものとして検索が続行されます。  
  
## <a name="see-also"></a>関連項目  
 [プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)
